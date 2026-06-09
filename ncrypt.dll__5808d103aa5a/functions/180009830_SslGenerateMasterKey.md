# SslGenerateMasterKey

- ea: `0x180009830`
- end: `0x180009a5d`
- name: `SslGenerateMasterKey`
- size: `557`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180009830`
- `0x180009a70`
- `0x180009cd0`
- `0x180009ea0`
- `0x18000a770`
- `0x18000c8e0`
- `0x18000d02c`
- `0x18000e120`
- `0x180020010`

## string_xrefs

- `0x180009988`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x1800099d8`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180009a1c`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180009a3b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslGenerateMasterKey(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        DWORD a5,
        int a6,
        __int64 a7,
        __int64 a8,
        int a9,
        __int64 a10,
        int a11)
{
  __int64 v13; // rbp
  __int64 v14; // r8
  __int64 v15; // rdi
  __int64 v16; // r10
  NCRYPT_KEY_HANDLE *v17; // rdx
  __int64 v18; // rsi
  NCryptKeyName **v19; // r8
  PVOID *v20; // r9
  _OWORD *v21; // rax
  _OWORD *v22; // rbx
  __int64 v23; // rdx
  int v24; // eax
  unsigned int v25; // edi

  v13 = ValidateSslKeyHandle(a2);
  v15 = ValidateSslKeyHandle(v14);
  v18 = ValidateSslProvHandle(v16);
  if ( v18 )
  {
    if ( v20 )
    {
      v21 = (_OWORD *)SafeAllocaAllocateFromHeap(32);
      v22 = v21;
      if ( v21 )
      {
        *v21 = 0;
        v21[1] = 0;
        if ( v15 )
          a3 = *(_QWORD *)(v15 + 16);
        if ( v13 )
          v23 = *(_QWORD *)(v13 + 16);
        else
          v23 = 0;
        v24 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _OWORD *, DWORD, int, __int64, __int64, int, __int64, int))(v18 + 128))(
                *(_QWORD *)(v18 + 424),
                v23,
                a3,
                v21 + 1,
                a5,
                a6,
                a7,
                a8,
                a9,
                a10,
                a11);
        v25 = v24;
        if ( v24 < 0 )
        {
          DebugTraceError(
            (unsigned int)v24,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
            2080);
          MSCryptFree(v22);
        }
        else
        {
          *(_DWORD *)v22 = 32;
          *(_QWORD *)((char *)v22 + 4) = 1145324610;
          *((_DWORD *)v22 + 3) = 1;
          *((_QWORD *)v22 + 3) = v18;
          _InterlockedIncrement((volatile signed __int32 *)(v18 + 16));
          *a4 = v22;
          v25 = 0;
        }
      }
      else
      {
        v25 = -2146893810;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)v17,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
            (unsigned int)"Status",
            14,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
            8);
      }
    }
    else
    {
      v25 = -2146893785;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)v17,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
          (unsigned int)"Status",
          39,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
          248);
    }
  }
  else
  {
    v25 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)v17,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        241);
  }
  return NormalizeNteStatus(v25, v17, v19, v20, a5);
}

```

## disassembly

```asm
0x180009830  push    rbx
0x180009832  push    rbp
0x180009833  push    rsi
0x180009834  push    rdi
0x180009835  push    r14
0x180009837  push    r15
0x180009839  sub     rsp, 68h
0x18000983d  mov     r10, rcx
0x180009840  mov     r14, r9
0x180009843  mov     rcx, rdx
0x180009846  mov     r15, r8
0x180009849  call    ValidateSslKeyHandle
0x18000984e  mov     rcx, r8
0x180009851  mov     rbp, rax
0x180009854  call    ValidateSslKeyHandle
0x180009859  mov     rcx, r10
0x18000985c  mov     rdi, rax
0x18000985f  call    ValidateSslProvHandle
0x180009864  mov     rsi, rax
0x180009867  test    rax, rax
0x18000986a  jz      loc_1800099EE
0x180009870  test    r9, r9
0x180009873  jz      loc_1800099AE
0x180009879  mov     ecx, 20h ; ' '
0x18000987e  call    SafeAllocaAllocateFromHeap
0x180009883  mov     rbx, rax
0x180009886  test    rax, rax
0x180009889  jz      loc_180009962
0x18000988f  xorps   xmm0, xmm0
0x180009892  movups  xmmword ptr [rax], xmm0
0x180009895  movups  xmmword ptr [rax+10h], xmm0
0x180009899  test    rdi, rdi
0x18000989c  jz      short loc_1800098A2
0x18000989e  mov     r15, [rdi+10h]
0x1800098a2  test    rbp, rbp
0x1800098a5  jz      loc_18000995B
0x1800098ab  mov     rdx, [rbp+10h]
0x1800098af  mov     rcx, [rsp+98h+arg_48]
0x1800098b7  lea     r9, [rax+10h]
0x1800098bb  mov     eax, [rsp+98h+arg_50]
0x1800098c2  mov     r8, r15
0x1800098c5  mov     [rsp+98h+var_48], eax
0x1800098c9  mov     rax, [rsi+80h]
0x1800098d0  mov     [rsp+98h+var_50], rcx
0x1800098d5  mov     ecx, [rsp+98h+arg_40]
0x1800098dc  mov     [rsp+98h+var_58], ecx
0x1800098e0  mov     rcx, [rsp+98h+arg_38]
0x1800098e8  mov     [rsp+98h+var_60], rcx
0x1800098ed  mov     rcx, [rsp+98h+arg_30]
0x1800098f5  mov     [rsp+98h+var_68], rcx
0x1800098fa  mov     ecx, [rsp+98h+arg_28]
0x180009901  mov     dword ptr [rsp+98h+var_70], ecx
0x180009905  mov     ecx, [rsp+98h+arg_20]
0x18000990c  mov     [rsp+98h+var_78], ecx
0x180009910  mov     rcx, [rsi+1A8h]
0x180009917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000991c  mov     edi, eax
0x18000991e  test    eax, eax
0x180009920  js      loc_180009A35
0x180009926  mov     dword ptr [rbx], 20h ; ' '
0x18000992c  mov     qword ptr [rbx+4], 44444442h
0x180009934  mov     dword ptr [rbx+0Ch], 1
0x18000993b  mov     [rbx+18h], rsi
0x18000993f  lock inc dword ptr [rsi+10h]
0x180009943  mov     [r14], rbx
0x180009946  xor     edi, edi
0x180009948  mov     ecx, edi
0x18000994a  add     rsp, 68h
0x18000994e  pop     r15
0x180009950  pop     r14
0x180009952  pop     rdi
0x180009953  pop     rsi
0x180009954  pop     rbp
0x180009955  pop     rbx
0x180009956  jmp     NormalizeNteStatus
0x18000995b  xor     edx, edx
0x18000995d  jmp     loc_1800098AF
0x180009962  mov     edi, 8009000Eh
0x180009967  mov     rcx, cs:WPP_GLOBAL_Control
0x18000996e  lea     rax, WPP_GLOBAL_Control
0x180009975  cmp     rcx, rax
0x180009978  jz      short loc_180009948
0x18000997a  test    byte ptr [rcx+1Ch], 1
0x18000997e  jz      short loc_180009948
0x180009980  mov     dword ptr [rsp+98h+var_68], 808h
0x180009988  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000998f  mov     [rsp+98h+var_70], r8
0x180009994  mov     [rsp+98h+var_78], 8009000Eh
0x18000999c  mov     rcx, [rcx+10h]
0x1800099a0  lea     r9, aStatus; "Status"
0x1800099a7  call    WPP_SF_sDsd
0x1800099ac  jmp     short loc_180009948
0x1800099ae  mov     edi, 80090027h
0x1800099b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099ba  lea     rax, WPP_GLOBAL_Control
0x1800099c1  cmp     rcx, rax
0x1800099c4  jz      short loc_180009948
0x1800099c6  test    byte ptr [rcx+1Ch], 1
0x1800099ca  jz      loc_180009948
0x1800099d0  mov     dword ptr [rsp+98h+var_68], 7F8h
0x1800099d8  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800099df  mov     [rsp+98h+var_70], r8
0x1800099e4  mov     [rsp+98h+var_78], 80090027h
0x1800099ec  jmp     short loc_18000999C
0x1800099ee  mov     edi, 80090026h
0x1800099f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099fa  lea     rax, WPP_GLOBAL_Control
0x180009a01  cmp     rcx, rax
0x180009a04  jz      loc_180009948
0x180009a0a  test    byte ptr [rcx+1Ch], 1
0x180009a0e  jz      loc_180009948
0x180009a14  mov     dword ptr [rsp+98h+var_68], 7F1h
0x180009a1c  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009a23  mov     [rsp+98h+var_70], r8
0x180009a28  mov     [rsp+98h+var_78], 80090026h
0x180009a30  jmp     loc_18000999C
0x180009a35  mov     r9d, 820h
0x180009a3b  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009a42  lea     rdx, aStatus; "Status"
0x180009a49  mov     ecx, eax
0x180009a4b  call    DebugTraceError
0x180009a50  mov     rcx, rbx
0x180009a53  call    MSCryptFree
0x180009a58  jmp     loc_180009948
```
