# DXGIAdapterCacheTelemetry::ExistingRegValueOnFailure<long &,long &,bool &>(long &,long &,bool &)

- ea: `0x1400035b8`
- end: `0x1400036b0`
- name: `??$ExistingRegValueOnFailure@AEAJAEAJAEA_N@DXGIAdapterCacheTelemetry@@SAXAEAJ0AEA_N@Z`
- size: `248`
- prototype: `__int64 __fastcall(int *, int *, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140011b91`

## callees

- `0x140001bac`
- `0x1400022a0`
- `0x1400035b8`
- `0x14000a9b4`

## pseudocode

```c
__int64 __fastcall DXGIAdapterCacheTelemetry::ExistingRegValueOnFailure<long &,long &,bool &>(
        int *a1,
        int *a2,
        char *a3)
{
  __int64 result; // rax
  __int64 v7; // r10
  char v8; // [rsp+30h] [rbp-59h] BYREF
  int v9; // [rsp+34h] [rbp-55h] BYREF
  int v10; // [rsp+38h] [rbp-51h] BYREF
  __int64 v11; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v12[32]; // [rsp+50h] [rbp-39h] BYREF
  int *v13; // [rsp+70h] [rbp-19h]
  __int64 v14; // [rsp+78h] [rbp-11h]
  int *v15; // [rsp+80h] [rbp-9h]
  __int64 v16; // [rsp+88h] [rbp-1h]
  char *v17; // [rsp+90h] [rbp+7h]
  __int64 v18; // [rsp+98h] [rbp+Fh]
  __int64 *v19; // [rsp+A0h] [rbp+17h]
  __int64 v20; // [rsp+A8h] [rbp+1Fh]

  result = (__int64)DXGIAdapterCacheLogging::Provider();
  v7 = result;
  if ( *(_DWORD *)result > 5u )
  {
    result = *(_QWORD *)(result + 24);
    if ( (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0 && (result & 0x400000000000LL) == result )
    {
      v8 = *a3;
      v9 = *a2;
      v10 = *a1;
      v19 = &v11;
      v17 = &v8;
      v15 = &v9;
      v13 = &v10;
      v11 = 0x1000000;
      v20 = 8;
      v18 = 1;
      v16 = 4;
      v14 = 4;
      return tlgWriteTransfer_EventWriteTransfer(v7, word_140015792, 0, 0, 6, v12);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400035b8  push    rbp
0x1400035ba  push    rbx
0x1400035bb  push    rsi
0x1400035bc  push    rdi
0x1400035bd  lea     rbp, [rsp-3Fh]
0x1400035c2  sub     rsp, 0C8h
0x1400035c9  mov     rax, cs:__security_cookie
0x1400035d0  xor     rax, rsp
0x1400035d3  mov     [rbp+57h+var_30], rax
0x1400035d7  mov     rbx, r8
0x1400035da  mov     rdi, rdx
0x1400035dd  mov     rsi, rcx
0x1400035e0  call    ?Provider@DXGIAdapterCacheLogging@@SAPEBU_tlgProvider_t@@XZ; DXGIAdapterCacheLogging::Provider(void)
0x1400035e5  mov     r10, rax
0x1400035e8  mov     r9d, [rax]
0x1400035eb  cmp     r9d, 5
0x1400035ef  jbe     loc_140003698
0x1400035f5  mov     rax, [rax+18h]
0x1400035f9  mov     rdx, 400000000000h
0x140003603  mov     r9, [r10+10h]
0x140003607  test    rdx, r9
0x14000360a  jz      loc_140003698
0x140003610  mov     rcx, rax
0x140003613  and     rcx, rdx
0x140003616  cmp     rcx, rax
0x140003619  jnz     short loc_140003698
0x14000361b  mov     al, [rbx]
0x14000361d  lea     rdx, word_140015792
0x140003624  mov     [rbp+57h+var_B0], al
0x140003627  xor     r9d, r9d
0x14000362a  mov     eax, [rdi]
0x14000362c  xor     r8d, r8d
0x14000362f  mov     [rbp+57h+var_AC], eax
0x140003632  mov     rcx, r10
0x140003635  mov     eax, [rsi]
0x140003637  mov     [rbp+57h+var_A8], eax
0x14000363a  lea     rax, [rbp+57h+var_A0]
0x14000363e  mov     [rbp+57h+var_40], rax
0x140003642  lea     rax, [rbp+57h+var_B0]
0x140003646  mov     [rbp+57h+var_50], rax
0x14000364a  lea     rax, [rbp+57h+var_AC]
0x14000364e  mov     [rbp+57h+var_60], rax
0x140003652  lea     rax, [rbp+57h+var_A8]
0x140003656  mov     [rbp+57h+var_70], rax
0x14000365a  lea     rax, [rbp+57h+var_90]
0x14000365e  mov     [rsp+0E0h+var_B8], rax
0x140003663  mov     [rsp+0E0h+var_C0], 6
0x14000366b  mov     [rbp+57h+var_A0], 1000000h
0x140003673  mov     [rbp+57h+var_38], 8
0x14000367b  mov     [rbp+57h+var_48], 1
0x140003683  mov     [rbp+57h+var_58], 4
0x14000368b  mov     [rbp+57h+var_68], 4
0x140003693  call    _tlgWriteTransfer_EventWriteTransfer
0x140003698  mov     rcx, [rbp+57h+var_30]
0x14000369c  xor     rcx, rsp; StackCookie
0x14000369f  call    __security_check_cookie
0x1400036a4  add     rsp, 0C8h
0x1400036ab  pop     rdi
0x1400036ac  pop     rsi
0x1400036ad  pop     rbx
0x1400036ae  pop     rbp
0x1400036af  retn
```
