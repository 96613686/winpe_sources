# RtlpGetBootStatusPathFromRegistry

- ea: `0x180110fa8`
- end: `0x180111160`
- name: `RtlpGetBootStatusPathFromRegistry`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1801414c0`

## callees

- `0x18001861c`
- `0x18001b984`
- `0x1800c0420`
- `0x180110fa8`
- `0x18012c830`
- `0x18015e4b0`
- `0x18015e510`
- `0x18015e5b0`
- `0x180163a80`

## string_xrefs

- `0x180110fd0`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Control`
- `0x180111054`: `OsBootstatPath`

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
0x180110fa8  push    rbp
0x180110faa  push    rbx
0x180110fab  push    rsi
0x180110fac  push    rdi
0x180110fad  push    r14
0x180110faf  mov     rbp, rsp
0x180110fb2  sub     rsp, 70h
0x180110fb6  xorps   xmm0, xmm0
0x180110fb9  mov     [rbp+arg_10], 0
0x180110fc0  xor     eax, eax
0x180110fc2  mov     [rbp+arg_8], 0
0x180110fc9  mov     r14, rcx
0x180110fcc  mov     [rbp+Handle], rax
0x180110fd0  lea     rcx, aRegistryMachin; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x180110fd7  mov     qword ptr [rbp+DestinationString.Length], rax
0x180110fdb  movups  [rbp+var_20], xmm0
0x180110fdf  mov     [rbp+DestinationString.Buffer], rcx
0x180110fe3  movups  [rbp+var_20+0Ch], xmm0
0x180110fe7  movups  [rbp+var_30], xmm0
0x180110feb  call    wcslen
0x180110ff0  add     rax, rax
0x180110ff3  mov     dword ptr [rbp+var_30], 30h ; '0'
0x180110ffa  cmp     rax, 0FFFEh
0x180111000  mov     qword ptr [rbp+var_30+8], 0
0x180111008  mov     ecx, 0FFFCh
0x18011100d  mov     dword ptr [rbp+var_20+8], 40h ; '@'
0x180111014  cmovnb  rax, rcx
0x180111018  lea     r8, [rbp+var_30]
0x18011101c  mov     [rbp+DestinationString.Length], ax
0x180111020  lea     rcx, [rbp+Handle]
0x180111024  xorps   xmm0, xmm0
0x180111027  mov     esi, 2
0x18011102c  add     ax, si
0x18011102f  mov     edx, 20019h
0x180111034  mov     [rbp+DestinationString.MaximumLength], ax
0x180111038  lea     rax, [rbp+DestinationString]
0x18011103c  mov     qword ptr [rbp+var_20], rax
0x180111040  movdqu  [rbp+var_10], xmm0
0x180111045  call    NtOpenKey
0x18011104a  mov     ebx, eax
0x18011104c  test    eax, eax
0x18011104e  js      loc_180111144
0x180111054  lea     rdx, aOsbootstatpath; "OsBootstatPath"
0x18011105b  lea     rcx, [rbp+DestinationString]; DestinationString
0x18011105f  call    RtlInitUnicodeString
0x180111064  mov     rcx, [rbp+Handle]
0x180111068  lea     rax, [rbp+arg_8]
0x18011106c  mov     [rsp+70h+var_48], rax
0x180111071  lea     rdx, [rbp+DestinationString]
0x180111075  xor     r9d, r9d
0x180111078  mov     [rsp+70h+var_50], 0
0x180111080  mov     r8d, esi
0x180111083  call    NtQueryValueKey
0x180111088  mov     ebx, eax
0x18011108a  cmp     eax, 0C0000023h
0x18011108f  jz      short loc_1801110A3
0x180111091  test    eax, eax
0x180111093  js      loc_180111144
0x180111099  mov     ebx, 0C0000001h
0x18011109e  jmp     loc_180111144
0x1801110a3  mov     rcx, gs:60h
0x1801110ac  xor     edx, edx
0x1801110ae  mov     r8d, [rbp+arg_8]
0x1801110b2  mov     rcx, [rcx+30h]
0x1801110b6  call    RtlAllocateHeap_0
0x1801110bb  mov     rdi, rax
0x1801110be  test    rax, rax
0x1801110c1  jnz     short loc_1801110CA
0x1801110c3  mov     ebx, 0C0000017h
0x1801110c8  jmp     short loc_180111144
0x1801110ca  mov     rcx, [rbp+Handle]
0x1801110ce  lea     rax, [rbp+arg_10]
0x1801110d2  mov     [rsp+70h+var_48], rax
0x1801110d7  lea     rdx, [rbp+DestinationString]
0x1801110db  mov     eax, [rbp+arg_8]
0x1801110de  mov     r9, rdi
0x1801110e1  mov     r8d, esi
0x1801110e4  mov     [rsp+70h+var_50], eax
0x1801110e8  call    NtQueryValueKey
0x1801110ed  mov     ebx, eax
0x1801110ef  test    eax, eax
0x1801110f1  js      short loc_18011112D
0x1801110f3  mov     rcx, gs:60h
0x1801110fc  xor     edx, edx
0x1801110fe  mov     r8d, [rdi+8]
0x180111102  mov     rcx, [rcx+30h]
0x180111106  call    RtlAllocateHeap_0
0x18011110b  mov     rsi, rax
0x18011110e  test    rax, rax
0x180111111  jnz     short loc_18011111A
0x180111113  mov     ebx, 0C0000017h
0x180111118  jmp     short loc_18011112D
0x18011111a  mov     r8d, [rdi+8]; Size
0x18011111e  lea     rdx, [rdi+0Ch]; Src
0x180111122  mov     rcx, rsi; void *
0x180111125  call    memmove
0x18011112a  mov     [r14], rsi
0x18011112d  mov     rcx, gs:60h
0x180111136  mov     r8, rdi
0x180111139  xor     edx, edx
0x18011113b  mov     rcx, [rcx+30h]
0x18011113f  call    RtlFreeHeap_0
0x180111144  mov     rcx, [rbp+Handle]; Handle
0x180111148  test    rcx, rcx
0x18011114b  jz      short loc_180111152
0x18011114d  call    NtClose
0x180111152  mov     eax, ebx
0x180111154  add     rsp, 70h
0x180111158  pop     r14
0x18011115a  pop     rdi
0x18011115b  pop     rsi
0x18011115c  pop     rbx
0x18011115d  pop     rbp
0x18011115e  retn
```
