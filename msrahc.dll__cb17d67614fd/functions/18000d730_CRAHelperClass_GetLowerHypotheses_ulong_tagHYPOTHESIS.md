# CRAHelperClass::GetLowerHypotheses(ulong *,tagHYPOTHESIS * *)

- ea: `0x18000d730`
- end: `0x18000da01`
- name: `?GetLowerHypotheses@CRAHelperClass@@UEAAJPEAKPEAPEAUtagHYPOTHESIS@@@Z`
- size: `721`
- prototype: `__int64 __fastcall(CRAHelperClass *this, struct _EVENT_DESCRIPTOR *, struct tagHYPOTHESIS **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000d3d4`
- `0x18000d730`
- `0x18000f5bc`
- `0x18000f7c8`
- `0x18000fc14`
- `0x180010184`
- `0x1800104f0`
- `0x180014660`

## string_xrefs

- `0x18000d797`: `UserSID`

## pseudocode

```c
__int64 __fastcall CRAHelperClass::GetLowerHypotheses(
        CRAHelperClass *this,
        struct _EVENT_DESCRIPTOR *a2,
        struct tagHYPOTHESIS **a3)
{
  unsigned int v6; // r9d
  unsigned int v8; // ebx
  struct _attribute_t *v9; // rax
  struct _attribute_t *v10; // rdx
  CEventLogger *v11; // rcx
  unsigned __int16 *v12; // rcx
  signed int v13; // eax
  const struct _EVENT_DESCRIPTOR *v14; // rdx
  CEventLogger *v15; // rcx
  unsigned int v16; // r9d
  const unsigned __int16 *v17; // rcx
  CEventLogger *v18; // rcx
  struct tagOCTET_STRING v19; // xmm0
  const unsigned __int16 *v20; // r8
  const unsigned __int16 *v21; // rax
  struct tagOCTET_STRING v22; // xmm0
  const unsigned __int16 *v23; // rcx
  struct tagOCTET_STRING v24; // [rsp+30h] [rbp-38h] BYREF

  if ( !a2 )
  {
    v6 = 920;
LABEL_3:
    CEventLogger::LogError(
      this,
      a2,
      L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
      v6,
      L"CRAHelperClass::GetLowerHypotheses",
      0x80070057);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    v6 = 921;
    goto LABEL_3;
  }
  v8 = 0;
  if ( *((_DWORD *)this + 43) != 1 )
  {
    v9 = _attributes_array_t::Find((CRAHelperClass *)((char *)this + 120), L"UserSID");
    v10 = v9;
    if ( *((_DWORD *)this + 40) == 1 )
    {
      if ( *((_DWORD *)this + 64) )
        return v8;
      v13 = BuildAAHypotheses((unsigned int *)&a2->Id, a3);
      v8 = v13;
      if ( v13 >= 0 )
        return v8;
      v16 = 946;
      goto LABEL_46;
    }
    v11 = (CEventLogger *)(unsigned int)(*((_DWORD *)this + 40) - 2);
    switch ( *((_DWORD *)this + 40) )
    {
      case 2:
        v21 = (const unsigned __int16 *)*((_QWORD *)this + 22);
        if ( !v21 )
        {
          v8 = -2147024809;
          CEventLogger::LogError(
            v11,
            (const struct _EVENT_DESCRIPTOR *)v10,
            L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
            0x3EEu,
            L"CRAHelperClass::GetLowerHypotheses",
            0x80070057);
          return v8;
        }
        if ( !v10 )
        {
          v8 = -2147024809;
          CEventLogger::LogError(
            v11,
            0,
            L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
            0x3F4u,
            L"CRAHelperClass::GetLowerHypotheses",
            0x80070057);
          return v8;
        }
        if ( *((_DWORD *)v10 + 2) == 14 )
          v22 = (struct tagOCTET_STRING)*((_OWORD *)v10 + 1);
        else
          v22 = (struct tagOCTET_STRING)xmmword_180020EA0;
        v23 = (const unsigned __int16 *)*((_QWORD *)this + 38);
        v24 = v22;
        v13 = BuildIncomingHypotheses(v23, v21, &v24, (unsigned int *)&a2->Id, a3);
        v8 = v13;
        if ( v13 >= 0 )
          return v8;
        v16 = 1022;
        goto LABEL_46;
      case 3:
        if ( *((_DWORD *)this + 84) == 10061 )
        {
          *((_DWORD *)this + 80) = 1;
          *(_OWORD *)((char *)this + 280) = RCG_RADIAG_EXPERT_FAQ;
          return v8;
        }
        v18 = (CEventLogger *)*((_QWORD *)this + 34);
        if ( !v18 )
        {
          v8 = -2147024809;
          CEventLogger::LogError(
            0,
            (const struct _EVENT_DESCRIPTOR *)v9,
            L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
            0x3D6u,
            L"CRAHelperClass::GetLowerHypotheses",
            0x80070057);
          return v8;
        }
        if ( !v9 )
        {
          v8 = -2147024809;
          CEventLogger::LogError(
            v18,
            0,
            L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
            0x3DCu,
            L"CRAHelperClass::GetLowerHypotheses",
            0x80070057);
          return v8;
        }
        if ( *((_DWORD *)v9 + 2) == 14 )
          v19 = (struct tagOCTET_STRING)*((_OWORD *)v9 + 1);
        else
          v19 = (struct tagOCTET_STRING)xmmword_180020EA0;
        v20 = (const unsigned __int16 *)*((_QWORD *)this + 22);
        v24 = v19;
        v13 = BuildFilteredOutgoingHypotheses((unsigned __int16 *)v18, &v24, v20, (unsigned int *)&a2->Id, a3);
        v8 = v13;
        if ( v13 >= 0 )
          return v8;
        v16 = 997;
        goto LABEL_46;
      case 4:
        v13 = BuildPNRPHypotheses(0, (unsigned int *)&a2->Id, a3);
        v8 = v13;
        if ( v13 >= 0 )
          return v8;
        v16 = 1060;
        goto LABEL_46;
      case 5:
        v17 = (const unsigned __int16 *)*((_QWORD *)this + 38);
        if ( !v17 )
        {
          v8 = -2147024809;
          CEventLogger::LogError(
            0,
            (const struct _EVENT_DESCRIPTOR *)v9,
            L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
            0x406u,
            L"CRAHelperClass::GetLowerHypotheses",
            0x80070057);
          return v8;
        }
        v13 = BuildPNRPHypotheses(v17, (unsigned int *)&a2->Id, a3);
        v8 = v13;
        if ( v13 >= 0 )
          return v8;
        v16 = 1038;
        goto LABEL_46;
      case 6:
        v12 = (unsigned __int16 *)*((_QWORD *)this + 39);
        if ( !v12 )
        {
          v8 = -2147024809;
          CEventLogger::LogError(
            0,
            (const struct _EVENT_DESCRIPTOR *)v9,
            L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
            0x416u,
            L"CRAHelperClass::GetLowerHypotheses",
            0x80070057);
          return v8;
        }
        v13 = BuildMultiPNRPHypotheses(v12, (unsigned int *)&a2->Id, a3);
        v8 = v13;
        if ( v13 >= 0 )
          return v8;
        v16 = 1053;
LABEL_46:
        CEventLogger::LogError(
          v15,
          v14,
          L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
          v16,
          L"CRAHelperClass::GetLowerHypotheses",
          v13);
        break;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18000d730  push    rbx
0x18000d732  push    rbp
0x18000d733  push    rsi
0x18000d734  push    rdi
0x18000d735  sub     rsp, 48h
0x18000d739  mov     rsi, r8
0x18000d73c  mov     rbp, rdx
0x18000d73f  mov     rdi, rcx
0x18000d742  test    rdx, rdx
0x18000d745  jnz     short loc_18000D777
0x18000d747  mov     r9d, 398h; unsigned int
0x18000d74d  lea     rax, aCrahelperclass_6; "CRAHelperClass::GetLowerHypotheses"
0x18000d754  mov     [rsp+68h+var_40], 80070057h; unsigned int
0x18000d75c  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18000d763  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x18000d768  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18000d76d  mov     eax, 80070057h
0x18000d772  jmp     loc_18000D9F8
0x18000d777  test    rsi, rsi
0x18000d77a  jnz     short loc_18000D784
0x18000d77c  mov     r9d, 399h
0x18000d782  jmp     short loc_18000D74D
0x18000d784  xor     ebx, ebx
0x18000d786  cmp     dword ptr [rcx+0ACh], 1
0x18000d78d  jz      loc_18000D9F6
0x18000d793  add     rcx, 78h ; 'x'; this
0x18000d797  lea     rdx, aUsersid; "UserSID"
0x18000d79e  call    ?Find@_attributes_array_t@@QEAAPEAV_attribute_t@@PEBG@Z; _attributes_array_t::Find(ushort const *)
0x18000d7a3  mov     ecx, [rdi+0A0h]
0x18000d7a9  mov     rdx, rax
0x18000d7ac  sub     ecx, 1
0x18000d7af  jz      loc_18000D9BB
0x18000d7b5  sub     ecx, 1
0x18000d7b8  jz      loc_18000D93A
0x18000d7be  sub     ecx, 1
0x18000d7c1  jz      loc_18000D888
0x18000d7c7  sub     ecx, 1
0x18000d7ca  jz      loc_18000D866
0x18000d7d0  sub     ecx, 1
0x18000d7d3  jz      short loc_18000D822
0x18000d7d5  cmp     ecx, 1
0x18000d7d8  jnz     loc_18000D9F6
0x18000d7de  mov     rcx, [rdi+138h]; unsigned __int16 *
0x18000d7e5  test    rcx, rcx
0x18000d7e8  jnz     short loc_18000D802
0x18000d7ea  mov     ebx, 80070057h
0x18000d7ef  mov     [rsp+68h+var_40], 80070057h
0x18000d7f7  mov     r9d, 416h
0x18000d7fd  jmp     loc_18000D9DE
0x18000d802  mov     r8, rsi; struct tagHYPOTHESIS **
0x18000d805  mov     rdx, rbp; unsigned int *
0x18000d808  call    ?BuildMultiPNRPHypotheses@@YAJPEAGPEAKPEAPEAUtagHYPOTHESIS@@@Z; BuildMultiPNRPHypotheses(ushort *,ulong *,tagHYPOTHESIS * *)
0x18000d80d  mov     ebx, eax
0x18000d80f  test    eax, eax
0x18000d811  jns     loc_18000D9F6
0x18000d817  mov     r9d, 41Dh
0x18000d81d  jmp     loc_18000D9DA
0x18000d822  mov     rcx, [rdi+130h]; unsigned __int16 *
0x18000d829  test    rcx, rcx
0x18000d82c  jnz     short loc_18000D846
0x18000d82e  mov     ebx, 80070057h
0x18000d833  mov     [rsp+68h+var_40], 80070057h
0x18000d83b  mov     r9d, 406h
0x18000d841  jmp     loc_18000D9DE
0x18000d846  mov     r8, rsi; struct tagHYPOTHESIS **
0x18000d849  mov     rdx, rbp; unsigned int *
0x18000d84c  call    ?BuildPNRPHypotheses@@YAJPEBGPEAKPEAPEAUtagHYPOTHESIS@@@Z; BuildPNRPHypotheses(ushort const *,ulong *,tagHYPOTHESIS * *)
0x18000d851  mov     ebx, eax
0x18000d853  test    eax, eax
0x18000d855  jns     loc_18000D9F6
0x18000d85b  mov     r9d, 40Eh
0x18000d861  jmp     loc_18000D9DA
0x18000d866  mov     r8, rsi; struct tagHYPOTHESIS **
0x18000d869  mov     rdx, rbp; unsigned int *
0x18000d86c  xor     ecx, ecx; unsigned __int16 *
0x18000d86e  call    ?BuildPNRPHypotheses@@YAJPEBGPEAKPEAPEAUtagHYPOTHESIS@@@Z; BuildPNRPHypotheses(ushort const *,ulong *,tagHYPOTHESIS * *)
0x18000d873  mov     ebx, eax
0x18000d875  test    eax, eax
0x18000d877  jns     loc_18000D9F6
0x18000d87d  mov     r9d, 424h
0x18000d883  jmp     loc_18000D9DA
0x18000d888  cmp     dword ptr [rdi+150h], 274Dh
0x18000d892  jnz     short loc_18000D8B2
0x18000d894  movups  xmm0, cs:RCG_RADIAG_EXPERT_FAQ
0x18000d89b  mov     dword ptr [rdi+140h], 1
0x18000d8a5  movdqu  xmmword ptr [rdi+118h], xmm0
0x18000d8ad  jmp     loc_18000D9F6
0x18000d8b2  mov     rcx, [rdi+110h]; unsigned __int16 *
0x18000d8b9  test    rcx, rcx
0x18000d8bc  jnz     short loc_18000D8D6
0x18000d8be  mov     ebx, 80070057h
0x18000d8c3  mov     [rsp+68h+var_40], 80070057h
0x18000d8cb  mov     r9d, 3D6h
0x18000d8d1  jmp     loc_18000D9DE
0x18000d8d6  test    rdx, rdx
0x18000d8d9  jnz     short loc_18000D8F3
0x18000d8db  mov     ebx, 80070057h
0x18000d8e0  mov     [rsp+68h+var_40], 80070057h
0x18000d8e8  mov     r9d, 3DCh
0x18000d8ee  jmp     loc_18000D9DE
0x18000d8f3  cmp     dword ptr [rax+8], 0Eh
0x18000d8f7  jnz     short loc_18000D8FF
0x18000d8f9  movups  xmm0, xmmword ptr [rax+10h]
0x18000d8fd  jmp     short loc_18000D906
0x18000d8ff  movups  xmm0, cs:xmmword_180020EA0
0x18000d906  mov     r8, [rdi+0B0h]; unsigned __int16 *
0x18000d90d  lea     rdx, [rsp+68h+var_38]; struct tagOCTET_STRING *
0x18000d912  mov     r9, rbp; unsigned int *
0x18000d915  movdqa  xmmword ptr [rsp+68h+var_38.dwLength], xmm0
0x18000d91b  mov     [rsp+68h+var_48], rsi; struct tagHYPOTHESIS **
0x18000d920  call    ?BuildFilteredOutgoingHypotheses@@YAJPEAGUtagOCTET_STRING@@PEBGPEAKPEAPEAUtagHYPOTHESIS@@@Z; BuildFilteredOutgoingHypotheses(ushort *,tagOCTET_STRING,ushort const *,ulong *,tagHYPOTHESIS * *)
0x18000d925  mov     ebx, eax
0x18000d927  test    eax, eax
0x18000d929  jns     loc_18000D9F6
0x18000d92f  mov     r9d, 3E5h
0x18000d935  jmp     loc_18000D9DA
0x18000d93a  mov     rax, [rdi+0B0h]
0x18000d941  test    rax, rax
0x18000d944  jnz     short loc_18000D95E
0x18000d946  mov     ebx, 80070057h
0x18000d94b  mov     [rsp+68h+var_40], 80070057h
0x18000d953  mov     r9d, 3EEh
0x18000d959  jmp     loc_18000D9DE
0x18000d95e  test    rdx, rdx
0x18000d961  jnz     short loc_18000D978
0x18000d963  mov     ebx, 80070057h
0x18000d968  mov     [rsp+68h+var_40], 80070057h
0x18000d970  mov     r9d, 3F4h
0x18000d976  jmp     short loc_18000D9DE
0x18000d978  cmp     dword ptr [rdx+8], 0Eh
0x18000d97c  jnz     short loc_18000D984
0x18000d97e  movups  xmm0, xmmword ptr [rdx+10h]
0x18000d982  jmp     short loc_18000D98B
0x18000d984  movups  xmm0, cs:xmmword_180020EA0
0x18000d98b  mov     rcx, [rdi+130h]; unsigned __int16 *
0x18000d992  lea     r8, [rsp+68h+var_38]; struct tagOCTET_STRING *
0x18000d997  mov     r9, rbp; unsigned int *
0x18000d99a  movdqa  xmmword ptr [rsp+68h+var_38.dwLength], xmm0
0x18000d9a0  mov     rdx, rax; unsigned __int16 *
0x18000d9a3  mov     [rsp+68h+var_48], rsi; struct tagHYPOTHESIS **
0x18000d9a8  call    ?BuildIncomingHypotheses@@YAJPEBG0UtagOCTET_STRING@@PEAKPEAPEAUtagHYPOTHESIS@@@Z; BuildIncomingHypotheses(ushort const *,ushort const *,tagOCTET_STRING,ulong *,tagHYPOTHESIS * *)
0x18000d9ad  mov     ebx, eax
0x18000d9af  test    eax, eax
0x18000d9b1  jns     short loc_18000D9F6
0x18000d9b3  mov     r9d, 3FEh
0x18000d9b9  jmp     short loc_18000D9DA
0x18000d9bb  cmp     [rdi+100h], ebx
0x18000d9c1  jnz     short loc_18000D9F6
0x18000d9c3  mov     rdx, rsi; struct tagHYPOTHESIS **
0x18000d9c6  mov     rcx, rbp; unsigned int *
0x18000d9c9  call    ?BuildAAHypotheses@@YAJPEAKPEAPEAUtagHYPOTHESIS@@@Z; BuildAAHypotheses(ulong *,tagHYPOTHESIS * *)
0x18000d9ce  mov     ebx, eax
0x18000d9d0  test    eax, eax
0x18000d9d2  jns     short loc_18000D9F6
0x18000d9d4  mov     r9d, 3B2h; unsigned int
0x18000d9da  mov     [rsp+68h+var_40], eax; unsigned int
0x18000d9de  lea     rax, aCrahelperclass_6; "CRAHelperClass::GetLowerHypotheses"
0x18000d9e5  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18000d9ec  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x18000d9f1  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18000d9f6  mov     eax, ebx
0x18000d9f8  add     rsp, 48h
0x18000d9fc  pop     rdi
0x18000d9fd  pop     rsi
0x18000d9fe  pop     rbp
0x18000d9ff  pop     rbx
0x18000da00  retn
```
