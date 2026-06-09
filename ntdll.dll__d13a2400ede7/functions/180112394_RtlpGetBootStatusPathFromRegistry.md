# RtlpGetBootStatusPathFromRegistry

- ea: `0x180112394`
- end: `0x18011254c`
- name: `RtlpGetBootStatusPathFromRegistry`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180141e50`

## callees

- `0x18001861c`
- `0x18001b984`
- `0x1800c4700`
- `0x180112394`
- `0x18012d320`
- `0x18015ecc0`
- `0x18015ed20`
- `0x18015edc0`
- `0x180164280`

## string_xrefs

- `0x1801123bc`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Control`
- `0x180112440`: `OsBootstatPath`

## pseudocode

```c
__int64 __fastcall RtlpGetBootStatusPathFromRegistry(_QWORD *a1)
{
  size_t v2; // rax
  int v3; // ebx
  int v4; // eax
  __int64 Heap_0; // rdi
  void *v6; // rax
  void *v7; // rsi
  UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  _DWORD v10[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v11; // [rsp+48h] [rbp-28h]
  UNICODE_STRING *p_DestinationString; // [rsp+50h] [rbp-20h]
  int v13; // [rsp+58h] [rbp-18h]
  _BYTE v14[20]; // [rsp+5Ch] [rbp-14h]
  unsigned int v15; // [rsp+A8h] [rbp+38h] BYREF
  int v16; // [rsp+B0h] [rbp+40h] BYREF
  HANDLE Handle; // [rsp+B8h] [rbp+48h] BYREF

  v16 = 0;
  v15 = 0;
  Handle = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  p_DestinationString = 0;
  DestinationString.Buffer = (wchar_t *)L"\\REGISTRY\\MACHINE\\SYSTEM\\CurrentControlSet\\Control";
  *(_OWORD *)v14 = 0;
  v10[1] = 0;
  v2 = 2 * wcslen(L"\\REGISTRY\\MACHINE\\SYSTEM\\CurrentControlSet\\Control");
  v10[0] = 48;
  v11 = 0;
  v13 = 64;
  if ( v2 >= 0xFFFE )
    LOWORD(v2) = -4;
  DestinationString.Length = v2;
  DestinationString.MaximumLength = v2 + 2;
  p_DestinationString = &DestinationString;
  *(_OWORD *)&v14[4] = 0;
  v3 = NtOpenKey(&Handle, 131097, v10);
  if ( v3 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"OsBootstatPath");
    v4 = NtQueryValueKey(Handle, &DestinationString, 2, 0, 0, &v15);
    v3 = v4;
    if ( v4 == -1073741789 )
    {
      Heap_0 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 0, v15);
      if ( Heap_0 )
      {
        v3 = NtQueryValueKey(Handle, &DestinationString, 2, Heap_0, v15, &v16);
        if ( v3 >= 0 )
        {
          v6 = (void *)RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 0, *(unsigned int *)(Heap_0 + 8));
          v7 = v6;
          if ( v6 )
          {
            memmove(v6, (const void *)(Heap_0 + 12), *(unsigned int *)(Heap_0 + 8));
            *a1 = v7;
          }
          else
          {
            v3 = -1073741801;
          }
        }
        RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, Heap_0);
      }
      else
      {
        v3 = -1073741801;
      }
    }
    else if ( v4 >= 0 )
    {
      v3 = -1073741823;
    }
  }
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180112394  push    rbp
0x180112396  push    rbx
0x180112397  push    rsi
0x180112398  push    rdi
0x180112399  push    r14
0x18011239b  mov     rbp, rsp
0x18011239e  sub     rsp, 70h
0x1801123a2  xorps   xmm0, xmm0
0x1801123a5  mov     [rbp+arg_10], 0
0x1801123ac  xor     eax, eax
0x1801123ae  mov     [rbp+arg_8], 0
0x1801123b5  mov     r14, rcx
0x1801123b8  mov     [rbp+Handle], rax
0x1801123bc  lea     rcx, aRegistryMachin; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x1801123c3  mov     qword ptr [rbp+DestinationString.Length], rax
0x1801123c7  movups  [rbp+var_20], xmm0
0x1801123cb  mov     [rbp+DestinationString.Buffer], rcx
0x1801123cf  movups  [rbp+var_20+0Ch], xmm0
0x1801123d3  movups  [rbp+var_30], xmm0
0x1801123d7  call    wcslen
0x1801123dc  add     rax, rax
0x1801123df  mov     dword ptr [rbp+var_30], 30h ; '0'
0x1801123e6  cmp     rax, 0FFFEh
0x1801123ec  mov     qword ptr [rbp+var_30+8], 0
0x1801123f4  mov     ecx, 0FFFCh
0x1801123f9  mov     dword ptr [rbp+var_20+8], 40h ; '@'
0x180112400  cmovnb  rax, rcx
0x180112404  lea     r8, [rbp+var_30]
0x180112408  mov     [rbp+DestinationString.Length], ax
0x18011240c  lea     rcx, [rbp+Handle]
0x180112410  xorps   xmm0, xmm0
0x180112413  mov     esi, 2
0x180112418  add     ax, si
0x18011241b  mov     edx, 20019h
0x180112420  mov     [rbp+DestinationString.MaximumLength], ax
0x180112424  lea     rax, [rbp+DestinationString]
0x180112428  mov     qword ptr [rbp+var_20], rax
0x18011242c  movdqu  [rbp+var_10], xmm0
0x180112431  call    NtOpenKey
0x180112436  mov     ebx, eax
0x180112438  test    eax, eax
0x18011243a  js      loc_180112530
0x180112440  lea     rdx, aOsbootstatpath; "OsBootstatPath"
0x180112447  lea     rcx, [rbp+DestinationString]; DestinationString
0x18011244b  call    RtlInitUnicodeString
0x180112450  mov     rcx, [rbp+Handle]
0x180112454  lea     rax, [rbp+arg_8]
0x180112458  mov     [rsp+70h+var_48], rax
0x18011245d  lea     rdx, [rbp+DestinationString]
0x180112461  xor     r9d, r9d
0x180112464  mov     [rsp+70h+var_50], 0
0x18011246c  mov     r8d, esi
0x18011246f  call    NtQueryValueKey
0x180112474  mov     ebx, eax
0x180112476  cmp     eax, 0C0000023h
0x18011247b  jz      short loc_18011248F
0x18011247d  test    eax, eax
0x18011247f  js      loc_180112530
0x180112485  mov     ebx, 0C0000001h
0x18011248a  jmp     loc_180112530
0x18011248f  mov     rcx, gs:60h
0x180112498  xor     edx, edx
0x18011249a  mov     r8d, [rbp+arg_8]
0x18011249e  mov     rcx, [rcx+30h]
0x1801124a2  call    RtlAllocateHeap_0
0x1801124a7  mov     rdi, rax
0x1801124aa  test    rax, rax
0x1801124ad  jnz     short loc_1801124B6
0x1801124af  mov     ebx, 0C0000017h
0x1801124b4  jmp     short loc_180112530
0x1801124b6  mov     rcx, [rbp+Handle]
0x1801124ba  lea     rax, [rbp+arg_10]
0x1801124be  mov     [rsp+70h+var_48], rax
0x1801124c3  lea     rdx, [rbp+DestinationString]
0x1801124c7  mov     eax, [rbp+arg_8]
0x1801124ca  mov     r9, rdi
0x1801124cd  mov     r8d, esi
0x1801124d0  mov     [rsp+70h+var_50], eax
0x1801124d4  call    NtQueryValueKey
0x1801124d9  mov     ebx, eax
0x1801124db  test    eax, eax
0x1801124dd  js      short loc_180112519
0x1801124df  mov     rcx, gs:60h
0x1801124e8  xor     edx, edx
0x1801124ea  mov     r8d, [rdi+8]
0x1801124ee  mov     rcx, [rcx+30h]
0x1801124f2  call    RtlAllocateHeap_0
0x1801124f7  mov     rsi, rax
0x1801124fa  test    rax, rax
0x1801124fd  jnz     short loc_180112506
0x1801124ff  mov     ebx, 0C0000017h
0x180112504  jmp     short loc_180112519
0x180112506  mov     r8d, [rdi+8]; Size
0x18011250a  lea     rdx, [rdi+0Ch]; Src
0x18011250e  mov     rcx, rsi; void *
0x180112511  call    memmove
0x180112516  mov     [r14], rsi
0x180112519  mov     rcx, gs:60h
0x180112522  mov     r8, rdi
0x180112525  xor     edx, edx
0x180112527  mov     rcx, [rcx+30h]
0x18011252b  call    RtlFreeHeap_0
0x180112530  mov     rcx, [rbp+Handle]; Handle
0x180112534  test    rcx, rcx
0x180112537  jz      short loc_18011253E
0x180112539  call    NtClose
0x18011253e  mov     eax, ebx
0x180112540  add     rsp, 70h
0x180112544  pop     r14
0x180112546  pop     rdi
0x180112547  pop     rsi
0x180112548  pop     rbx
0x180112549  pop     rbp
0x18011254a  retn
```
