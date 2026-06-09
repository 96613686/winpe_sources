# PmQueryGlobalSettings(_CONTROL_EXTENSION *)

- ea: `0x140029078`
- end: `0x14002929c`
- name: `?PmQueryGlobalSettings@@YAJPEAU_CONTROL_EXTENSION@@@Z`
- size: `548`
- prototype: `__int64 __fastcall(struct _CONTROL_EXTENSION *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1400292a4`

## callees

- `0x140020050`
- `0x140029078`

## import_xrefs

- `ntoskrnl!IoOpenDriverRegistryKey` at `0x1400290fa`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x14002917f`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x1400290fa`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x14002917f`
- `ntoskrnl!ZwClose` at `0x14002914e`
- `ntoskrnl!ZwClose` at `0x1400291d4`
- `ntoskrnl!ZwClose` at `0x14002914e`
- `ntoskrnl!ZwClose` at `0x1400291d4`
- `ntoskrnl!ExIsSoftBoot` at `0x140029244`
- `ntoskrnl!ExIsSoftBoot` at `0x140029244`
- `ntoskrnl!RtlCheckRegistryKey` at `0x140029222`
- `ntoskrnl!RtlCheckRegistryKey` at `0x140029222`
- `ntoskrnl!IoGetBootDiskInformationLite` at `0x14002925d`
- `ntoskrnl!IoGetBootDiskInformationLite` at `0x14002925d`
- `ntoskrnl!IoGetBootLayers` at `0x1400290a8`
- `ntoskrnl!IoGetBootLayers` at `0x1400290a8`
- `HAL!KeQueryPerformanceCounter` at `0x140029276`
- `HAL!KeQueryPerformanceCounter` at `0x140029276`

## pseudocode

```c
__int64 __fastcall PmQueryGlobalSettings(struct _CONTROL_EXTENSION *a1)
{
  NTSTATUS BootLayers; // ebx
  bool v3; // al
  __int64 v4; // rcx
  _DWORD *v5; // rsi
  _DWORD *v6; // r12
  int Parameter; // r15d
  int v8; // r14d
  NTSTATUS v9; // eax
  HANDLE Handle; // [rsp+68h] [rbp+38h] BYREF
  __int64 v12; // [rsp+70h] [rbp+40h] BYREF

  Handle = 0;
  v12 = 0;
  BootLayers = IoGetBootLayers(&v12);
  if ( BootLayers >= 0 )
  {
    v3 = *(_DWORD *)v12 == 3 && (*(_DWORD *)(v12 + 44) & 1) != 0 && **(_DWORD **)(v12 + 8) == 1;
    v4 = *((_QWORD *)a1 + 1);
    *((_BYTE *)a1 + 440) = v3;
    BootLayers = IoOpenDriverRegistryKey(v4, 1, 1, 0, &Handle);
    if ( BootLayers >= 0 )
    {
      v5 = (_DWORD *)((char *)a1 + 160);
      v6 = (_DWORD *)((char *)a1 + 164);
      Parameter = PmGetParameter(Handle, &SanPolicy, (unsigned int *)a1 + 40);
      v8 = PmGetParameter(Handle, &ConflictPolicy, (unsigned int *)a1 + 41);
      ZwClose(Handle);
      if ( Parameter == -1073741772 || v8 == -1073741772 )
      {
        BootLayers = IoOpenDriverRegistryKey(*((_QWORD *)a1 + 1), 0, 1, 0, &Handle);
        if ( BootLayers < 0 )
          return (unsigned int)BootLayers;
        if ( Parameter == -1073741772 )
          Parameter = PmGetParameter(Handle, &SanPolicy, (unsigned int *)a1 + 40);
        if ( v8 == -1073741772 )
          v8 = PmGetParameter(Handle, &ConflictPolicy, (unsigned int *)a1 + 41);
        ZwClose(Handle);
      }
      if ( Parameter < 0 || (unsigned int)(*v5 - 1) > 5 )
        *v5 = 1;
      if ( v8 < 0 || (unsigned int)(*v6 - 1) > 2 )
        *v6 = 2;
      if ( *((_BYTE *)a1 + 440) )
        *v5 = 5;
      v9 = RtlCheckRegistryKey(2u, (PWSTR)L"MiniNT");
      BootLayers = v9;
      if ( v9 < 0 )
      {
        if ( v9 != -1073741772 )
          return (unsigned int)BootLayers;
      }
      else
      {
        *((_BYTE *)a1 + 168) = 1;
      }
      *((_BYTE *)a1 + 169) = ExIsSoftBoot();
      BootLayers = IoGetBootDiskInformationLite((PBOOTDISK_INFORMATION_LITE *)a1 + 24);
      if ( BootLayers >= 0 )
        KeQueryPerformanceCounter((PLARGE_INTEGER)a1 + 54);
    }
  }
  return (unsigned int)BootLayers;
}

```

## disassembly

```asm
0x140029078  mov     [rsp-28h+arg_0], rbx
0x14002907d  mov     [rsp-28h+arg_18], rsi
0x140029082  push    rbp
0x140029083  push    rdi
0x140029084  push    r12
0x140029086  push    r14
0x140029088  push    r15
0x14002908a  mov     rbp, rsp
0x14002908d  sub     rsp, 30h
0x140029091  mov     rdi, rcx
0x140029094  mov     [rbp+Handle], 0
0x14002909c  lea     rcx, [rbp+arg_10]
0x1400290a0  mov     [rbp+arg_10], 0
0x1400290a8  call    cs:__imp_IoGetBootLayers
0x1400290af  nop     dword ptr [rax+rax+00h]
0x1400290b4  mov     ebx, eax
0x1400290b6  test    eax, eax
0x1400290b8  js      loc_140029282
0x1400290be  mov     rcx, [rbp+arg_10]
0x1400290c2  mov     edx, 1
0x1400290c7  cmp     dword ptr [rcx], 3
0x1400290ca  jnz     short loc_1400290DF
0x1400290cc  mov     eax, [rcx+2Ch]
0x1400290cf  test    dl, al
0x1400290d1  jz      short loc_1400290DF
0x1400290d3  mov     rax, [rcx+8]
0x1400290d7  cmp     [rax], edx
0x1400290d9  jnz     short loc_1400290DF
0x1400290db  mov     al, dl
0x1400290dd  jmp     short loc_1400290E1
0x1400290df  xor     eax, eax
0x1400290e1  mov     rcx, [rdi+8]
0x1400290e5  xor     r9d, r9d
0x1400290e8  mov     [rdi+1B8h], al
0x1400290ee  mov     r8d, edx
0x1400290f1  lea     rax, [rbp+Handle]
0x1400290f5  mov     [rsp+30h+var_10], rax
0x1400290fa  call    cs:__imp_IoOpenDriverRegistryKey
0x140029101  nop     dword ptr [rax+rax+00h]
0x140029106  mov     ebx, eax
0x140029108  test    eax, eax
0x14002910a  js      loc_140029282
0x140029110  mov     rcx, [rbp+Handle]; void *
0x140029114  lea     rsi, [rdi+0A0h]
0x14002911b  mov     r8, rsi; unsigned int *
0x14002911e  lea     rdx, ?SanPolicy@@3U_UNICODE_STRING@@A; struct _UNICODE_STRING *
0x140029125  call    ?PmGetParameter@@YAJPEAXPEAU_UNICODE_STRING@@PEAK@Z; PmGetParameter(void *,_UNICODE_STRING *,ulong *)
0x14002912a  mov     rcx, [rbp+Handle]; void *
0x14002912e  lea     r12, [rdi+0A4h]
0x140029135  mov     r8, r12; unsigned int *
0x140029138  lea     rdx, ?ConflictPolicy@@3U_UNICODE_STRING@@A; struct _UNICODE_STRING *
0x14002913f  mov     r15d, eax
0x140029142  call    ?PmGetParameter@@YAJPEAXPEAU_UNICODE_STRING@@PEAK@Z; PmGetParameter(void *,_UNICODE_STRING *,ulong *)
0x140029147  mov     rcx, [rbp+Handle]; Handle
0x14002914b  mov     r14d, eax
0x14002914e  call    cs:__imp_ZwClose
0x140029155  nop     dword ptr [rax+rax+00h]
0x14002915a  mov     ebx, 0C0000034h
0x14002915f  cmp     r15d, ebx
0x140029162  jz      short loc_140029169
0x140029164  cmp     r14d, ebx
0x140029167  jnz     short loc_1400291E0
0x140029169  mov     rcx, [rdi+8]
0x14002916d  lea     rax, [rbp+Handle]
0x140029171  xor     r9d, r9d
0x140029174  mov     [rsp+30h+var_10], rax
0x140029179  xor     edx, edx
0x14002917b  lea     r8d, [r9+1]
0x14002917f  call    cs:__imp_IoOpenDriverRegistryKey
0x140029186  nop     dword ptr [rax+rax+00h]
0x14002918b  mov     ebx, eax
0x14002918d  test    eax, eax
0x14002918f  js      loc_140029282
0x140029195  mov     ebx, 0C0000034h
0x14002919a  cmp     r15d, ebx
0x14002919d  jnz     short loc_1400291B5
0x14002919f  mov     rcx, [rbp+Handle]; void *
0x1400291a3  lea     rdx, ?SanPolicy@@3U_UNICODE_STRING@@A; struct _UNICODE_STRING *
0x1400291aa  mov     r8, rsi; unsigned int *
0x1400291ad  call    ?PmGetParameter@@YAJPEAXPEAU_UNICODE_STRING@@PEAK@Z; PmGetParameter(void *,_UNICODE_STRING *,ulong *)
0x1400291b2  mov     r15d, eax
0x1400291b5  cmp     r14d, ebx
0x1400291b8  jnz     short loc_1400291D0
0x1400291ba  mov     rcx, [rbp+Handle]; void *
0x1400291be  lea     rdx, ?ConflictPolicy@@3U_UNICODE_STRING@@A; struct _UNICODE_STRING *
0x1400291c5  mov     r8, r12; unsigned int *
0x1400291c8  call    ?PmGetParameter@@YAJPEAXPEAU_UNICODE_STRING@@PEAK@Z; PmGetParameter(void *,_UNICODE_STRING *,ulong *)
0x1400291cd  mov     r14d, eax
0x1400291d0  mov     rcx, [rbp+Handle]; Handle
0x1400291d4  call    cs:__imp_ZwClose
0x1400291db  nop     dword ptr [rax+rax+00h]
0x1400291e0  test    r15d, r15d
0x1400291e3  js      short loc_1400291EE
0x1400291e5  mov     eax, [rsi]
0x1400291e7  dec     eax
0x1400291e9  cmp     eax, 5
0x1400291ec  jbe     short loc_1400291F4
0x1400291ee  mov     dword ptr [rsi], 1
0x1400291f4  mov     ecx, 2; RelativeTo
0x1400291f9  test    r14d, r14d
0x1400291fc  js      short loc_140029208
0x1400291fe  mov     eax, [r12]
0x140029202  dec     eax
0x140029204  cmp     eax, ecx
0x140029206  jbe     short loc_14002920C
0x140029208  mov     [r12], ecx
0x14002920c  cmp     byte ptr [rdi+1B8h], 0
0x140029213  jz      short loc_14002921B
0x140029215  mov     dword ptr [rsi], 5
0x14002921b  lea     rdx, Path; "MiniNT"
0x140029222  call    cs:__imp_RtlCheckRegistryKey
0x140029229  nop     dword ptr [rax+rax+00h]
0x14002922e  mov     ebx, eax
0x140029230  test    eax, eax
0x140029232  js      short loc_14002923D
0x140029234  mov     byte ptr [rdi+0A8h], 1
0x14002923b  jmp     short loc_140029244
0x14002923d  cmp     eax, 0C0000034h
0x140029242  jnz     short loc_140029282
0x140029244  call    cs:__imp_ExIsSoftBoot
0x14002924b  nop     dword ptr [rax+rax+00h]
0x140029250  lea     rcx, [rdi+0C0h]; BootDiskInformation
0x140029257  mov     [rdi+0A9h], al
0x14002925d  call    cs:__imp_IoGetBootDiskInformationLite
0x140029264  nop     dword ptr [rax+rax+00h]
0x140029269  mov     ebx, eax
0x14002926b  test    eax, eax
0x14002926d  js      short loc_140029282
0x14002926f  lea     rcx, [rdi+1B0h]; PerformanceFrequency
0x140029276  call    cs:__imp_KeQueryPerformanceCounter
0x14002927d  nop     dword ptr [rax+rax+00h]
0x140029282  mov     rsi, [rsp+30h+arg_18]
0x140029287  mov     eax, ebx
0x140029289  mov     rbx, [rsp+30h+arg_0]
0x14002928e  add     rsp, 30h
0x140029292  pop     r15
0x140029294  pop     r14
0x140029296  pop     r12
0x140029298  pop     rdi
0x140029299  pop     rbp
0x14002929a  retn
```
