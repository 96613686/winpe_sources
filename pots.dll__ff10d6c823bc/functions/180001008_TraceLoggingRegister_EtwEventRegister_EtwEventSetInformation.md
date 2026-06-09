# TraceLoggingRegister_EtwEventRegister_EtwEventSetInformation

- ea: `0x180001008`
- end: `0x1800010b8`
- name: `TraceLoggingRegister_EtwEventRegister_EtwEventSetInformation`
- size: `176`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004670`
- `0x180004710`

## callees

- `0x180001008`
- `0x180004930`

## import_xrefs

- `ntdll!EtwEventRegister` at `0x18000106a`
- `ntdll!EtwEventRegister` at `0x18000106a`
- `ntdll!EtwEventSetInformation` at `0x180001093`
- `ntdll!EtwEventSetInformation` at `0x180001093`

## pseudocode

```c
__int64 __fastcall TraceLoggingRegister_EtwEventRegister_EtwEventSetInformation(_QWORD *a1)
{
  _QWORD *v1; // rsi
  bool v2; // zf
  int v4; // eax
  unsigned int v5; // ebx
  __int128 v7; // [rsp+20h] [rbp-28h] BYREF

  v1 = a1 + 4;
  v2 = a1[4] == 0;
  v7 = *(_OWORD *)(a1[1] - 16LL);
  if ( !v2 )
    __fastfail(5u);
  a1[5] = 0;
  a1[6] = 0;
  v4 = ((__int64 (__fastcall *)(__int128 *, __int64 (__fastcall *)(int, int, int, int, __int64, __int64, __int64), _QWORD *, _QWORD *))EtwEventRegister)(
         &v7,
         tlgEnableCallback,
         a1,
         a1 + 4);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      return (unsigned __int16)v4 | 0x80070000;
  }
  else
  {
    EtwEventSetInformation(*v1, 2, a1[1], *(unsigned __int16 *)a1[1], v7, *((_QWORD *)&v7 + 1));
  }
  return v5;
}

```

## disassembly

```asm
0x180001008  mov     [rsp+arg_8], rbx
0x18000100d  mov     [rsp+arg_10], rsi
0x180001012  push    rdi
0x180001013  sub     rsp, 40h
0x180001017  mov     rax, cs:__security_cookie
0x18000101e  xor     rax, rsp
0x180001021  mov     [rsp+48h+var_18], rax
0x180001026  mov     rax, [rcx+8]
0x18000102a  lea     rsi, [rcx+20h]
0x18000102e  cmp     qword ptr [rsi], 0
0x180001032  mov     rdi, rcx
0x180001035  movups  xmm0, xmmword ptr [rax-10h]
0x180001039  movdqu  [rsp+48h+var_28], xmm0
0x18000103f  jz      short loc_180001048
0x180001041  mov     ecx, 5
0x180001046  int     29h; Win8: RtlFailFast(ecx)
0x180001048  mov     r9, rsi
0x18000104b  mov     qword ptr [rdi+28h], 0
0x180001053  mov     r8, rdi
0x180001056  mov     qword ptr [rdi+30h], 0
0x18000105e  lea     rdx, _tlgEnableCallback
0x180001065  lea     rcx, [rsp+48h+var_28]
0x18000106a  call    cs:__imp_EtwEventRegister
0x180001070  mov     ebx, eax
0x180001072  test    eax, eax
0x180001074  jz      short loc_180001083
0x180001076  jle     short loc_180001099
0x180001078  movzx   ebx, ax
0x18000107b  or      ebx, 80070000h
0x180001081  jmp     short loc_180001099
0x180001083  mov     r8, [rdi+8]
0x180001087  mov     edx, 2
0x18000108c  mov     rcx, [rsi]
0x18000108f  movzx   r9d, word ptr [r8]
0x180001093  call    cs:__imp_EtwEventSetInformation
0x180001099  mov     eax, ebx
0x18000109b  mov     rcx, [rsp+48h+var_18]
0x1800010a0  xor     rcx, rsp; StackCookie
0x1800010a3  call    __security_check_cookie
0x1800010a8  mov     rbx, [rsp+48h+arg_8]
0x1800010ad  mov     rsi, [rsp+48h+arg_10]
0x1800010b2  add     rsp, 40h
0x1800010b6  pop     rdi
0x1800010b7  retn
```
