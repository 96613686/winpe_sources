# CCscNetApiInterfaceImpl::NetServerEnumEx(ushort const *,ulong,uchar * *,ulong,ulong *,ulong *,ulong,ushort const *,ushort const *)

- ea: `0x1800062b0`
- end: `0x180006459`
- name: `?NetServerEnumEx@CCscNetApiInterfaceImpl@@UEAAEPEBGKPEAPEAEKPEAK2K00@Z`
- size: `425`
- prototype: `unsigned __int8 __fastcall(CCscNetApiInterfaceImpl *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int8 **, unsigned int, unsigned int *, unsigned int *, unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800062a0`

## callees

- `0x1800062b0`
- `0x18000882c`
- `0x180008b74`
- `0x180009462`
- `0x180009490`

## pseudocode

```c
unsigned __int8 __fastcall CCscNetApiInterfaceImpl::NetServerEnumEx(
        CCscNetApiInterfaceImpl *this,
        const unsigned __int16 *a2,
        char a3,
        unsigned __int8 **a4,
        char a5,
        unsigned int *a6,
        unsigned int *a7,
        char a8,
        const unsigned __int16 *a9,
        const unsigned __int16 *a10)
{
  int v11; // ebp
  __int64 v13; // rdx
  __int64 v14; // r8
  int v16; // [rsp+30h] [rbp-348h]
  _BYTE v17[560]; // [rsp+100h] [rbp-278h] BYREF

  v11 = (int)a2;
  memset_0(v17, 0, 0x226u);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u )
  {
    WPP_SF_SDDDSS(*((_QWORD *)WPP_GLOBAL_Control + 27), v13, v14, v11, a3, a5, a8, (__int64)a9, (__int64)a10);
  }
  *a4 = 0;
  *a6 = 0;
  *a7 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u )
  {
    LOBYTE(v16) = 78;
    WPP_SF_qDDcD(*((_QWORD *)WPP_GLOBAL_Control + 27), v13, v14, *a4, *a6, 0, v16, 4077);
  }
  return 0;
}

```

## disassembly

```asm
0x1800062b0  mov     [rsp+arg_0], rbx
0x1800062b5  push    rbp
0x1800062b6  push    rsi
0x1800062b7  push    rdi
0x1800062b8  push    r12
0x1800062ba  push    r13
0x1800062bc  push    r14
0x1800062be  push    r15
0x1800062c0  sub     rsp, 340h
0x1800062c7  mov     rax, cs:__security_cookie
0x1800062ce  xor     rax, rsp
0x1800062d1  mov     [rsp+378h+var_48], rax
0x1800062d9  mov     rdi, [rsp+378h+arg_28]
0x1800062e1  lea     rcx, [rsp+378h+var_278]; void *
0x1800062e9  mov     rsi, [rsp+378h+arg_30]
0x1800062f1  mov     r14d, r8d
0x1800062f4  mov     r15, [rsp+378h+arg_40]
0x1800062fc  mov     rbp, rdx
0x1800062ff  mov     r12, [rsp+378h+arg_48]
0x180006307  xor     edx, edx; Val
0x180006309  mov     r8d, 226h; Size
0x18000630f  mov     rbx, r9
0x180006312  call    memset_0
0x180006317  xorps   xmm0, xmm0
0x18000631a  mov     [rsp+378h+var_308], 28h ; '('
0x180006322  lea     rax, [rsp+378h+var_2C8]
0x18000632a  mov     [rsp+378h+var_2D8], 0FFFFFFFFh
0x180006335  xor     r13d, r13d
0x180006338  mov     [rsp+378h+var_310], rax
0x18000633d  lea     rax, ??_7CDescriptor_SERVER_INFO@@6B@; const CDescriptor_SERVER_INFO::`vftable'
0x180006344  mov     [rsp+378h+var_2D4], r13d
0x18000634c  mov     [rsp+378h+var_318], rax
0x180006351  movups  [rsp+378h+var_328], xmm0
0x180006356  mov     [rsp+378h+var_2D0], r13b
0x18000635e  movups  [rsp+378h+var_2F8], xmm0
0x180006366  movups  [rsp+378h+var_2E8], xmm0
0x18000636e  movups  [rsp+378h+var_298], xmm0
0x180006376  movups  [rsp+378h+var_288], xmm0
0x18000637e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006385  lea     rax, WPP_GLOBAL_Control
0x18000638c  cmp     rcx, rax
0x18000638f  jz      short loc_1800063DE
0x180006391  test    byte ptr [rcx+0E4h], 1
0x180006398  jz      short loc_1800063DE
0x18000639a  cmp     byte ptr [rcx+0E1h], 4
0x1800063a1  jb      short loc_1800063DE
0x1800063a3  mov     eax, dword ptr [rsp+378h+arg_38]
0x1800063aa  mov     r9, rbp
0x1800063ad  mov     rcx, [rcx+0D8h]
0x1800063b4  mov     [rsp+378h+var_338], r12
0x1800063b9  mov     [rsp+378h+var_340], r15
0x1800063be  mov     [rsp+378h+var_348], eax
0x1800063c2  mov     eax, dword ptr [rsp+378h+arg_20]
0x1800063c9  mov     [rsp+378h+var_350], eax
0x1800063cd  mov     [rsp+378h+var_358], r14d
0x1800063d2  call    WPP_SF_SDDDSS
0x1800063d7  lea     rax, WPP_GLOBAL_Control
0x1800063de  mov     [rbx], r13
0x1800063e1  mov     [rdi], r13d
0x1800063e4  mov     [rsi], r13d
0x1800063e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063ee  cmp     rcx, rax
0x1800063f1  jz      short loc_18000642C
0x1800063f3  test    byte ptr [rcx+0E4h], 1
0x1800063fa  jz      short loc_18000642C
0x1800063fc  cmp     byte ptr [rcx+0E1h], 4
0x180006403  jb      short loc_18000642C
0x180006405  mov     eax, [rdi]
0x180006407  mov     r9, [rbx]
0x18000640a  mov     rcx, [rcx+0D8h]
0x180006411  mov     dword ptr [rsp+378h+var_340], 0FEDh
0x180006419  mov     byte ptr [rsp+378h+var_348], 4Eh ; 'N'
0x18000641e  mov     [rsp+378h+var_350], r13d
0x180006423  mov     [rsp+378h+var_358], eax
0x180006427  call    WPP_SF_qDDcD
0x18000642c  xor     al, al
0x18000642e  mov     rcx, [rsp+378h+var_48]
0x180006436  xor     rcx, rsp; StackCookie
0x180006439  call    __security_check_cookie
0x18000643e  mov     rbx, [rsp+378h+arg_0]
0x180006446  add     rsp, 340h
0x18000644d  pop     r15
0x18000644f  pop     r14
0x180006451  pop     r13
0x180006453  pop     r12
0x180006455  pop     rdi
0x180006456  pop     rsi
0x180006457  pop     rbp
0x180006458  retn
```
