# FatFastQueryNetworkOpenInfo

- ea: `0x140039220`
- end: `0x1400393f0`
- name: `FatFastQueryNetworkOpenInfo`
- size: `464`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140039220`
- `0x140039400`
- `0x14003d880`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140039289`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140039289`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400392bb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400393dc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400392bb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400393dc`
- `ntoskrnl!ExLocalTimeToSystemTime` at `0x1400392ec`
- `ntoskrnl!ExLocalTimeToSystemTime` at `0x1400392ec`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400393d0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400393d0`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400392ab`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400392ab`

## pseudocode

```c
char __fastcall FatFastQueryNetworkOpenInfo(__int64 a1, BOOLEAN a2, union _LARGE_INTEGER *a3, __int64 a4)
{
  char v8; // r14
  char v9; // si
  __int64 v10; // rdi
  DWORD v11; // ecx
  union _LARGE_INTEGER v12; // rax
  union _LARGE_INTEGER v13; // rax
  union _LARGE_INTEGER v14; // rax
  __int64 v15; // [rsp+20h] [rbp-58h] BYREF
  __int64 v16; // [rsp+28h] [rbp-50h] BYREF
  _QWORD v17[9]; // [rsp+30h] [rbp-48h] BYREF

  v17[0] = 0;
  v15 = 0;
  v16 = 0;
  if ( (unsigned int)FatDecodeFileObject(a1, v17, &v15, &v16) - 2 > 1 )
    return 0;
  v8 = 0;
  v9 = 0;
  KeEnterCriticalRegion();
  v10 = v15;
  if ( (*(_DWORD *)(v15 + 192) & 4) == 0 )
  {
    if ( !ExAcquireResourceSharedLite(*(PERESOURCE *)(v15 + 8), a2) )
    {
      KeLeaveCriticalRegion();
      return 0;
    }
    v9 = 1;
  }
  if ( *(_DWORD *)(v10 + 196) == 1 )
  {
    ExLocalTimeToSystemTime(&FatJanOne1980, a3 + 3);
    v11 = *(unsigned __int8 *)(v10 + 546);
    a3[6].LowPart = v11;
    if ( *(_WORD *)v10 == 1284 )
    {
      v12 = a3[3];
      a3[2] = v12;
      a3[1] = v12;
      *a3 = v12;
    }
    else
    {
      a3[2] = *(union _LARGE_INTEGER *)(v10 + 272);
      *a3 = *(union _LARGE_INTEGER *)(v10 + 256);
      a3[1] = *(union _LARGE_INTEGER *)(v10 + 264);
    }
    if ( (*(_DWORD *)(v10 + 192) & 0x20) != 0 )
      a3[6].LowPart = v11 | 0x100;
    if ( (*(_DWORD *)(*(_QWORD *)(v10 + 184) + 200LL) & 0x400000) != 0 && (*(_DWORD *)(v10 + 192) & 0x20000) != 0 )
      a3[6].LowPart |= 0x4000u;
    if ( !a3[6].LowPart )
      a3[6].LowPart = 128;
    if ( *(_WORD *)v10 != 1282 )
    {
      a3[4] = FatLargeZero;
      v14 = FatLargeZero;
      goto LABEL_22;
    }
    v13 = *(union _LARGE_INTEGER *)(v10 + 24);
    if ( v13.QuadPart != -1 )
    {
      a3[4] = v13;
      v14 = *(union _LARGE_INTEGER *)(v10 + 32);
LABEL_22:
      a3[5] = v14;
      *(_DWORD *)a4 = 0;
      *(_QWORD *)(a4 + 8) = 56;
      v8 = 1;
    }
  }
  if ( v9 )
    ExReleaseResourceLite(*(PERESOURCE *)(v10 + 8));
  KeLeaveCriticalRegion();
  return v8;
}

```

## disassembly

```asm
0x140039220  mov     rax, rsp
0x140039223  push    rbx
0x140039224  push    rsi
0x140039225  push    rdi
0x140039226  push    r12
0x140039228  push    r14
0x14003922a  push    r15
0x14003922c  sub     rsp, 48h
0x140039230  mov     r12, r9
0x140039233  mov     rbx, r8
0x140039236  mov     r15b, dl
0x140039239  mov     qword ptr [rax-48h], 0
0x140039241  mov     qword ptr [rax-58h], 0
0x140039249  mov     qword ptr [rax-50h], 0
0x140039251  lea     r9, [rax-50h]
0x140039255  lea     r8, [rax-58h]
0x140039259  lea     rdx, [rax-48h]
0x14003925d  call    FatDecodeFileObject
0x140039262  add     eax, 0FFFFFFFEh
0x140039265  cmp     eax, 1
0x140039268  jbe     short loc_14003927B
0x14003926a  xor     al, al
0x14003926c  add     rsp, 48h
0x140039270  pop     r15
0x140039272  pop     r14
0x140039274  pop     r12
0x140039276  pop     rdi
0x140039277  pop     rsi
0x140039278  pop     rbx
0x140039279  retn
0x14003927b  xor     r14b, r14b
0x14003927e  xor     sil, sil
0x140039281  mov     [rsp+78h+arg_8], sil
0x140039289  call    cs:__imp_KeEnterCriticalRegion
0x140039290  nop     dword ptr [rax+rax+00h]
0x140039295  mov     rdi, [rsp+78h+var_58]
0x14003929a  mov     eax, [rdi+0C0h]
0x1400392a0  test    al, 4
0x1400392a2  jnz     short loc_1400392D4
0x1400392a4  mov     dl, r15b; Wait
0x1400392a7  mov     rcx, [rdi+8]; Resource
0x1400392ab  call    cs:__imp_ExAcquireResourceSharedLite
0x1400392b2  nop     dword ptr [rax+rax+00h]
0x1400392b7  test    al, al
0x1400392b9  jnz     short loc_1400392C9
0x1400392bb  call    cs:__imp_KeLeaveCriticalRegion
0x1400392c2  nop     dword ptr [rax+rax+00h]
0x1400392c7  jmp     short loc_14003926A
0x1400392c9  mov     sil, 1
0x1400392cc  mov     [rsp+78h+arg_8], sil
0x1400392d4  cmp     dword ptr [rdi+0C4h], 1
0x1400392db  jnz     loc_1400393C7
0x1400392e1  lea     rdx, [rbx+18h]; SystemTime
0x1400392e5  lea     rcx, FatJanOne1980; LocalTime
0x1400392ec  call    cs:__imp_ExLocalTimeToSystemTime
0x1400392f3  nop     dword ptr [rax+rax+00h]
0x1400392f8  movzx   ecx, byte ptr [rdi+222h]
0x1400392ff  mov     [rbx+30h], ecx
0x140039302  mov     eax, 504h
0x140039307  cmp     [rdi], ax
0x14003930a  jnz     short loc_14003931D
0x14003930c  mov     rax, [rbx+18h]
0x140039310  mov     [rbx+10h], rax
0x140039314  mov     [rbx+8], rax
0x140039318  mov     [rbx], rax
0x14003931b  jmp     short loc_14003933D
0x14003931d  mov     rax, [rdi+110h]
0x140039324  mov     [rbx+10h], rax
0x140039328  mov     rax, [rdi+100h]
0x14003932f  mov     [rbx], rax
0x140039332  mov     rax, [rdi+108h]
0x140039339  mov     [rbx+8], rax
0x14003933d  mov     eax, [rdi+0C0h]
0x140039343  test    al, 20h
0x140039345  jz      short loc_14003934E
0x140039347  bts     ecx, 8
0x14003934b  mov     [rbx+30h], ecx
0x14003934e  mov     rax, [rdi+0B8h]
0x140039355  mov     ecx, [rax+0C8h]
0x14003935b  bt      ecx, 16h
0x14003935f  jnb     short loc_140039372
0x140039361  test    dword ptr [rdi+0C0h], 20000h
0x14003936b  jz      short loc_140039372
0x14003936d  bts     dword ptr [rbx+30h], 0Eh
0x140039372  cmp     dword ptr [rbx+30h], 0
0x140039376  jnz     short loc_14003937F
0x140039378  mov     dword ptr [rbx+30h], 80h
0x14003937f  mov     eax, 502h
0x140039384  cmp     [rdi], ax
0x140039387  jnz     short loc_14003939D
0x140039389  mov     rax, [rdi+18h]
0x14003938d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140039391  jz      short loc_1400393C7
0x140039393  mov     [rbx+20h], rax
0x140039397  mov     rax, [rdi+20h]
0x14003939b  jmp     short loc_1400393AF
0x14003939d  mov     rax, qword ptr cs:FatLargeZero
0x1400393a4  mov     [rbx+20h], rax
0x1400393a8  mov     rax, qword ptr cs:FatLargeZero
0x1400393af  mov     [rbx+28h], rax
0x1400393b3  mov     dword ptr [r12], 0
0x1400393bb  mov     qword ptr [r12+8], 38h ; '8'
0x1400393c4  mov     r14b, 1
0x1400393c7  test    sil, sil
0x1400393ca  jz      short loc_1400393DC
0x1400393cc  mov     rcx, [rdi+8]; Resource
0x1400393d0  call    cs:__imp_ExReleaseResourceLite
0x1400393d7  nop     dword ptr [rax+rax+00h]
0x1400393dc  call    cs:__imp_KeLeaveCriticalRegion
0x1400393e3  nop     dword ptr [rax+rax+00h]
0x1400393e8  mov     al, r14b
0x1400393eb  jmp     loc_14003926C
0x14005e262  push    rbp
0x14005e264  sub     rsp, 20h
0x14005e268  mov     rbp, rdx
0x14005e26b  cmp     byte ptr [rbp+88h], 0
0x14005e272  jz      short loc_14005E289
0x14005e274  mov     rcx, [rbp+20h]
0x14005e278  mov     rcx, [rcx+8]; Resource
0x14005e27c  call    cs:__imp_ExReleaseResourceLite
0x14005e283  nop     dword ptr [rax+rax+00h]
0x14005e288  nop
0x14005e289  call    cs:__imp_KeLeaveCriticalRegion
0x14005e290  nop     dword ptr [rax+rax+00h]
0x14005e295  nop
0x14005e296  add     rsp, 20h
0x14005e29a  pop     rbp
0x14005e29b  retn
```
