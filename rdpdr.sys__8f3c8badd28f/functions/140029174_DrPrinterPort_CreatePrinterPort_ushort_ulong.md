# DrPrinterPort::CreatePrinterPort(ushort *,ulong)

- ea: `0x140029174`
- end: `0x140029221`
- name: `?CreatePrinterPort@DrPrinterPort@@QEAAJPEAGK@Z`
- size: `173`
- prototype: `__int64 __fastcall(DrPrinterPort *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14001e3f0`

## callees

- `0x140006480`
- `0x140029174`
- `0x1400294a0`
- `0x140029aa8`

## pseudocode

```c
__int64 __fastcall DrPrinterPort::CreatePrinterPort(DrPrinterPort *this, unsigned __int16 *a2)
{
  int v2; // edi
  __int64 result; // rax
  __int64 v5; // [rsp+28h] [rbp-D0h]
  struct _UNICODE_STRING v6; // [rsp+40h] [rbp-B8h] BYREF
  char v7; // [rsp+50h] [rbp-A8h] BYREF

  v2 = (int)a2;
  *(_QWORD *)&v6.Length = 9175040;
  v6.Buffer = (wchar_t *)&v7;
  DrDevice::CreateReferenceString(this, &v6);
  result = RDPDRPRT_RegisterPrinterPortInterface(
             *((_QWORD *)this + 4) + 748LL,
             *(_DWORD *)(*((_QWORD *)this + 4) + 1128LL),
             (const char *)this + 48,
             (__int64)&v6,
             v2,
             v5,
             (struct _UNICODE_STRING *)((char *)this + 72),
             (unsigned int *)this + 17);
  if ( (_DWORD)result )
    *((_DWORD *)this + 17) = 0;
  return result;
}

```

## disassembly

```asm
0x140029174  mov     [rsp+arg_10], rbx
0x140029179  mov     [rsp+arg_18], rsi
0x14002917e  push    rdi
0x14002917f  sub     rsp, 0F0h
0x140029186  mov     rax, cs:__security_cookie
0x14002918d  xor     rax, rsp
0x140029190  mov     [rsp+0F8h+var_18], rax
0x140029198  mov     rdi, rdx
0x14002919b  mov     qword ptr [rsp+0F8h+var_B8.Length], 8C0000h
0x1400291a4  lea     rax, [rsp+0F8h+var_A8]
0x1400291a9  mov     rbx, rcx
0x1400291ac  lea     rdx, [rsp+0F8h+var_B8]; struct _UNICODE_STRING *
0x1400291b1  mov     [rsp+0F8h+var_B8.Buffer], rax
0x1400291b6  call    ?CreateReferenceString@DrDevice@@QEAAXPEAU_UNICODE_STRING@@@Z; DrDevice::CreateReferenceString(_UNICODE_STRING *)
0x1400291bb  mov     rdx, [rbx+20h]
0x1400291bf  lea     rax, [rbx+48h]
0x1400291c3  lea     rsi, [rbx+44h]
0x1400291c7  mov     [rsp+0F8h+var_C0], rsi
0x1400291cc  lea     r8, [rbx+30h]
0x1400291d0  mov     [rsp+0F8h+var_C8], rax
0x1400291d5  lea     r9, [rsp+0F8h+var_B8]
0x1400291da  lea     rcx, [rdx+2ECh]
0x1400291e1  mov     [rsp+0F8h+var_D8], rdi
0x1400291e6  mov     edx, [rdx+468h]
0x1400291ec  call    RDPDRPRT_RegisterPrinterPortInterface
0x1400291f1  test    eax, eax
0x1400291f3  jz      short loc_1400291FB
0x1400291f5  mov     dword ptr [rsi], 0
0x1400291fb  mov     rcx, [rsp+0F8h+var_18]
0x140029203  xor     rcx, rsp; StackCookie
0x140029206  call    __security_check_cookie
0x14002920b  lea     r11, [rsp+0F8h+var_8]
0x140029213  mov     rbx, [r11+20h]
0x140029217  mov     rsi, [r11+28h]
0x14002921b  mov     rsp, r11
0x14002921e  pop     rdi
0x14002921f  retn
```
