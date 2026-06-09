# Microsoft::HostGuardian::Client::Plugin::AttestationHandler::AttestShs(std::vector<AttestationResultType,std::allocator<AttestationResultType>> const &,ShsAttestationFlag &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,uint *,AttestationResult * *)

- ea: `0x180008bd0`
- end: `0x180008d10`
- name: `?AttestShs@AttestationHandler@Plugin@Client@HostGuardian@Microsoft@@AEAA?AW4AttestationError@@AEBV?$vector@W4AttestationResultType@@V?$allocator@W4AttestationResultType@@@std@@@std@@AEAW4ShsAttestationFlag@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@8@PEAIPEAPEAUAttestationResult@@@Z`
- size: `320`
- prototype: `__int64 __fastcall(__int64, int, __int64, char **, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007c80`

## callees

- `0x180008a90`
- `0x180008bd0`
- `0x180008d18`
- `0x18000a8b0`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::Plugin::AttestationHandler::AttestShs(
        __int64 a1,
        int a2,
        __int64 a3,
        char **a4,
        __int64 a5,
        __int64 a6)
{
  unsigned int v10; // ebp
  __int64 v11; // r8
  char **v12; // r9
  char *v13; // rdx
  char *v14; // rbp
  __int64 v15; // rbx
  _QWORD *v16; // r9
  char *v17; // rdx
  char *v18; // rsi
  __int64 v19; // rbx

  v10 = Microsoft::HostGuardian::Client::Plugin::AttestationHandler::AttestShsInternal(
          a1,
          a2,
          *(_QWORD *)a1,
          *(_DWORD *)(*(_QWORD *)a1 + 116LL),
          a3,
          a5,
          a6);
  if ( v10 + 2063724543 > 2 || (v12 = *(char ***)(*(_QWORD *)a1 + 64LL), v12 == *(char ***)(*(_QWORD *)a1 + 72LL)) )
  {
    v16 = *(_QWORD **)a1;
    if ( a4 != *(char ***)a1 )
    {
      v17 = (char *)v16[2];
      if ( v16[3] > 7u )
        v16 = (_QWORD *)*v16;
      if ( v17 > a4[3] )
      {
        std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(a4, v17, v11, v16);
      }
      else
      {
        if ( (unsigned __int64)a4[3] <= 7 )
          v18 = (char *)a4;
        else
          v18 = *a4;
        v19 = 2LL * (_QWORD)v17;
        a4[2] = v17;
        memmove_0(v18, v16, 2LL * (_QWORD)v17);
        *(_WORD *)&v18[v19] = 0;
      }
    }
  }
  else
  {
    if ( a4 != v12 )
    {
      v13 = v12[2];
      if ( (unsigned __int64)v12[3] > 7 )
        v12 = (char **)*v12;
      if ( v13 > a4[3] )
      {
        std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(a4, v13, v11, v12);
      }
      else
      {
        if ( (unsigned __int64)a4[3] <= 7 )
          v14 = (char *)a4;
        else
          v14 = *a4;
        v15 = 2LL * (_QWORD)v13;
        a4[2] = v13;
        memmove_0(v14, v12, 2LL * (_QWORD)v13);
        *(_WORD *)&v14[v15] = 0;
      }
    }
    return (unsigned int)Microsoft::HostGuardian::Client::Plugin::AttestationHandler::AttestShsInternal(
                           a1,
                           a2,
                           (_DWORD)a4,
                           *(_DWORD *)(*(_QWORD *)a1 + 116LL),
                           a3,
                           a5,
                           a6);
  }
  return v10;
}

```

## disassembly

```asm
0x180008bd0  push    rbx
0x180008bd2  push    rbp
0x180008bd3  push    rsi
0x180008bd4  push    rdi
0x180008bd5  push    r12
0x180008bd7  push    r13
0x180008bd9  push    r14
0x180008bdb  push    r15
0x180008bdd  sub     rsp, 48h
0x180008be1  mov     r12, [rsp+88h+arg_28]
0x180008be9  mov     r14, r8
0x180008bec  mov     r8, [rcx]
0x180008bef  mov     rdi, r9
0x180008bf2  mov     r13, [rsp+88h+arg_20]
0x180008bfa  mov     r15, rdx
0x180008bfd  mov     [rsp+88h+var_58], r12
0x180008c02  mov     rsi, rcx
0x180008c05  mov     [rsp+88h+var_60], r13
0x180008c0a  mov     r9d, [r8+74h]
0x180008c0e  mov     [rsp+88h+var_68], r14
0x180008c13  call    ?AttestShsInternal@AttestationHandler@Plugin@Client@HostGuardian@Microsoft@@AEAA?AW4AttestationError@@AEBV?$vector@W4AttestationResultType@@V?$allocator@W4AttestationResultType@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@8@IAEAW4ShsAttestationFlag@@PEAIPEAPEAUAttestationResult@@@Z; Microsoft::HostGuardian::Client::Plugin::AttestationHandler::AttestShsInternal(std::vector<AttestationResultType> const &,std::wstring const &,uint,ShsAttestationFlag &,uint *,AttestationResult * *)
0x180008c18  mov     ebp, eax
0x180008c1a  lea     edx, [rax+7B01EFFFh]
0x180008c20  cmp     edx, 2
0x180008c23  ja      loc_180008CAC
0x180008c29  mov     rcx, [rsi]
0x180008c2c  mov     r9, [rcx+40h]
0x180008c30  cmp     r9, [rcx+48h]
0x180008c34  jz      short loc_180008CAC
0x180008c36  cmp     rdi, r9
0x180008c39  jz      short loc_180008C84
0x180008c3b  cmp     qword ptr [r9+18h], 7
0x180008c40  mov     rdx, [r9+10h]
0x180008c44  jbe     short loc_180008C49
0x180008c46  mov     r9, [r9]
0x180008c49  cmp     rdx, [rdi+18h]
0x180008c4d  ja      short loc_180008C7C
0x180008c4f  cmp     qword ptr [rdi+18h], 7
0x180008c54  jbe     short loc_180008C5B
0x180008c56  mov     rbp, [rdi]
0x180008c59  jmp     short loc_180008C5E
0x180008c5b  mov     rbp, rdi
0x180008c5e  lea     rbx, [rdx+rdx]
0x180008c62  mov     [rdi+10h], rdx
0x180008c66  mov     r8, rbx; Size
0x180008c69  mov     rdx, r9; Src
0x180008c6c  mov     rcx, rbp; void *
0x180008c6f  call    memmove_0
0x180008c74  xor     eax, eax
0x180008c76  mov     [rbx+rbp], ax
0x180008c7a  jmp     short loc_180008C84
0x180008c7c  mov     rcx, rdi
0x180008c7f  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x180008c84  mov     r9, [rsi]
0x180008c87  mov     r8, rdi
0x180008c8a  mov     [rsp+88h+var_58], r12
0x180008c8f  mov     rdx, r15
0x180008c92  mov     [rsp+88h+var_60], r13
0x180008c97  mov     rcx, rsi
0x180008c9a  mov     [rsp+88h+var_68], r14
0x180008c9f  mov     r9d, [r9+74h]
0x180008ca3  call    ?AttestShsInternal@AttestationHandler@Plugin@Client@HostGuardian@Microsoft@@AEAA?AW4AttestationError@@AEBV?$vector@W4AttestationResultType@@V?$allocator@W4AttestationResultType@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@8@IAEAW4ShsAttestationFlag@@PEAIPEAPEAUAttestationResult@@@Z; Microsoft::HostGuardian::Client::Plugin::AttestationHandler::AttestShsInternal(std::vector<AttestationResultType> const &,std::wstring const &,uint,ShsAttestationFlag &,uint *,AttestationResult * *)
0x180008ca8  mov     ebp, eax
0x180008caa  jmp     short loc_180008CFD
0x180008cac  mov     r9, [rsi]
0x180008caf  cmp     rdi, r9
0x180008cb2  jz      short loc_180008CFD
0x180008cb4  cmp     qword ptr [r9+18h], 7
0x180008cb9  mov     rdx, [r9+10h]
0x180008cbd  jbe     short loc_180008CC2
0x180008cbf  mov     r9, [r9]
0x180008cc2  cmp     rdx, [rdi+18h]
0x180008cc6  ja      short loc_180008CF5
0x180008cc8  cmp     qword ptr [rdi+18h], 7
0x180008ccd  jbe     short loc_180008CD4
0x180008ccf  mov     rsi, [rdi]
0x180008cd2  jmp     short loc_180008CD7
0x180008cd4  mov     rsi, rdi
0x180008cd7  lea     rbx, [rdx+rdx]
0x180008cdb  mov     [rdi+10h], rdx
0x180008cdf  mov     r8, rbx; Size
0x180008ce2  mov     rdx, r9; Src
0x180008ce5  mov     rcx, rsi; void *
0x180008ce8  call    memmove_0
0x180008ced  xor     eax, eax
0x180008cef  mov     [rbx+rsi], ax
0x180008cf3  jmp     short loc_180008CFD
0x180008cf5  mov     rcx, rdi
0x180008cf8  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x180008cfd  mov     eax, ebp
0x180008cff  add     rsp, 48h
0x180008d03  pop     r15
0x180008d05  pop     r14
0x180008d07  pop     r13
0x180008d09  pop     r12
0x180008d0b  pop     rdi
0x180008d0c  pop     rsi
0x180008d0d  pop     rbp
0x180008d0e  pop     rbx
0x180008d0f  retn
```
