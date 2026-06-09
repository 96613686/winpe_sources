# ExternalAuthNames::onSyncRequest(IRequest *)

- ea: `0x180022ae0`
- end: `0x180022ee7`
- name: `?onSyncRequest@ExternalAuthNames@@MEAA?AW4_IASREQUESTSTATUS@@PEAUIRequest@@@Z`
- size: `1031`
- prototype: `enum _IASREQUESTSTATUS __high(struct IRequest *)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000acf4`
- `0x18000b24c`
- `0x18000ba5c`
- `0x18000c28c`
- `0x18000c4a4`
- `0x18000c500`
- `0x18000c808`
- `0x18000d55c`
- `0x18000d5d8`
- `0x18000e754`
- `0x180016884`
- `0x1800169e0`
- `0x18002110c`
- `0x1800213d0`
- `0x180022ae0`
- `0x1800254a0`
- `0x18002e010`

## import_xrefs

- `msvcrt!_wcsupr` at `0x180022d67`
- `msvcrt!_wcsupr` at `0x180022d67`
- `msvcrt!wcschr` at `0x180022d52`
- `msvcrt!wcschr` at `0x180022d52`
- `KERNEL32!GetLastError` at `0x180022c48`
- `KERNEL32!GetLastError` at `0x180022c5c`
- `KERNEL32!GetLastError` at `0x180022c48`
- `KERNEL32!GetLastError` at `0x180022c5c`
- `KERNEL32!LocalFree` at `0x180022e97`
- `KERNEL32!LocalFree` at `0x180022e97`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180022c26`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180022c26`

## string_xrefs

- `0x180022c50`: `Error ConvertSidToStringSid failed %x`
- `0x180022ce0`: `SID received %S`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall ExternalAuthNames::onSyncRequest(__int64 a1, struct IRequest *a2)
{
  unsigned int v4; // ebx
  void *v6; // rdi
  bool v7; // dl
  NameMapper *v8; // rcx
  int v9; // r9d
  void *v10; // rbx
  const unsigned __int16 *v11; // rax
  const wchar_t *v12; // rcx
  wchar_t *v13; // r13
  int v14; // r9d
  LPVOID v15; // [rsp+30h] [rbp-68h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-60h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp-58h] BYREF
  LPVOID v18[2]; // [rsp+48h] [rbp-50h] BYREF
  _BYTE v19[8]; // [rsp+58h] [rbp-40h] BYREF
  struct IAttributesRaw *v20; // [rsp+60h] [rbp-38h]
  unsigned int v21; // [rsp+B0h] [rbp+18h] BYREF
  unsigned int v22; // [rsp+B8h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Entering ExternalAuthNames stage");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_73a3aabcfd463fffdec8169cd7ccfd67_Traceguids, "NPSSVC");
  }
  StringSid = 0;
  IASTL::IASRequest::IASRequest((IASTL::IASRequest *)v19, a2);
  pv = 0;
  if ( (unsigned __int8)IASTL::IASAttribute::load(&pv, v20, 4168, 1) && *((_DWORD *)pv + 6) )
  {
    v21 = 4155;
    IASTL::IASRequest::RemoveAttributesByType((IASTL::IASRequest *)v19, 1u, &v21);
    IASTL::IASAttribute::store((IASTL::IASAttribute *)(a1 + 88), v20);
    if ( (unsigned __int8)IASTL::IASAttribute::load(&pv, v20, 4167, 6) )
    {
      v6 = pv;
      if ( !ConvertSidToStringSidW(*((PSID *)pv + 4), &StringSid) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          GetLastError();
          WppDbgPrint("Error ConvertSidToStringSid failed %x");
          GetLastError();
          WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_73a3aabcfd463fffdec8169cd7ccfd67_Traceguids);
        }
        _com_issue_error(8);
      }
      v18[0] = 0;
      IASTL::IASAttribute::load(v18, v20, 4169, 5);
      IASTL::IASAttribute::IASAttribute((IASTL::IASAttribute *)&v15, v7);
      *((_DWORD *)v15 + 2) = 4129;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("SID received %S");
        WPP_SF_sS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          (unsigned int)WPP_73a3aabcfd463fffdec8169cd7ccfd67_Traceguids,
          v9,
          (__int64)StringSid);
      }
      v10 = v18[0];
      if ( v18[0] )
        v11 = (const unsigned __int16 *)*((_QWORD *)v18[0] + 4);
      else
        v11 = 0;
      NameMapper::mapName(v8, StringSid, (struct IASTL::IASAttribute *)&v15, DS_SID_OR_SID_HISTORY_NAME, v11);
      v12 = (const wchar_t *)*((_QWORD *)v15 + 4);
      if ( v12 )
      {
        v13 = wcschr(v12, 0x5Cu);
        *v13 = 0;
        _wcsupr(*((wchar_t **)v15 + 4));
        *v13 = 92;
      }
      IASTL::IASAttribute::store((IASTL::IASAttribute *)&v15, v20);
      IASStoreFQUserName(v20, DS_NT4_ACCOUNT_NAME, *((const unsigned __int16 **)v15 + 4));
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("SAM-Account-Name is \"%S\".");
        WPP_SF_sS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)WPP_73a3aabcfd463fffdec8169cd7ccfd67_Traceguids,
          v14,
          *((_QWORD *)v15 + 4));
      }
      v22 = 4167;
      IASTL::IASRequest::RemoveAttributesByType((IASTL::IASRequest *)v19, 1u, &v22);
      if ( v15 )
        IASAttributeRelease(v15);
      if ( v10 )
        IASAttributeRelease(v10);
      IASAttributeRelease(v6);
      (*(void (__fastcall **)(struct IAttributesRaw *))(*(_QWORD *)v20 + 16LL))(v20);
      if ( StringSid )
        LocalFree(StringSid);
      return 2;
    }
    else
    {
      v4 = NameMapper::onSyncRequest(a1, a2);
      if ( pv )
        IASAttributeRelease(pv);
      (*(void (__fastcall **)(struct IAttributesRaw *, _QWORD))(*(_QWORD *)v20 + 16LL))(v20, *(_QWORD *)v20);
      return v4;
    }
  }
  else
  {
    if ( pv )
      IASAttributeRelease(pv);
    (*(void (__fastcall **)(struct IAttributesRaw *))(*(_QWORD *)v20 + 16LL))(v20);
    return 2;
  }
}

```

## disassembly

```asm
0x180022ae0  mov     [rsp+arg_0], rbx
0x180022ae5  mov     [rsp+arg_8], rdx
0x180022aea  push    rsi
0x180022aeb  push    rdi
0x180022aec  push    r12
0x180022aee  push    r13
0x180022af0  push    r15
0x180022af2  sub     rsp, 70h
0x180022af6  mov     r15, rdx
0x180022af9  mov     rbx, rcx
0x180022afc  lea     r13, WPP_GLOBAL_Control
0x180022b03  mov     rax, cs:WPP_GLOBAL_Control
0x180022b0a  cmp     rax, r13
0x180022b0d  jz      short loc_180022B4A
0x180022b0f  cmp     byte ptr [rax+19h], 4
0x180022b13  jb      short loc_180022B4A
0x180022b15  test    byte ptr [rax+1Ch], 4
0x180022b19  jz      short loc_180022B4A
0x180022b1b  lea     rcx, aEnteringExtern; "Entering ExternalAuthNames stage"
0x180022b22  call    WppDbgPrint
0x180022b27  mov     edx, 0Ah
0x180022b2c  lea     r9, aNpssvc; "NPSSVC"
0x180022b33  lea     r8, WPP_73a3aabcfd463fffdec8169cd7ccfd67_Traceguids
0x180022b3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b41  mov     rcx, [rcx+10h]
0x180022b45  call    WPP_SF_s
0x180022b4a  xor     esi, esi
0x180022b4c  mov     r12d, esi
0x180022b4f  mov     [rsp+98h+StringSid], rsi
0x180022b54  mov     rdx, r15; struct IRequest *
0x180022b57  lea     rcx, [rsp+98h+var_40]; this
0x180022b5c  call    ??0IASRequest@IASTL@@QEAA@PEAUIRequest@@@Z; IASTL::IASRequest::IASRequest(IRequest *)
0x180022b61  nop
0x180022b62  mov     [rsp+98h+pv], rsi
0x180022b67  lea     edi, [rsi+1]
0x180022b6a  mov     r9d, edi
0x180022b6d  mov     r8d, 1048h
0x180022b73  mov     rdx, [rsp+98h+var_38]
0x180022b78  lea     rcx, [rsp+98h+pv]
0x180022b7d  call    ?load@IASAttribute@IASTL@@QEAA_NPEAUIAttributesRaw@@KW4IASTYPEENUM@@@Z; IASTL::IASAttribute::load(IAttributesRaw *,ulong,IASTYPEENUM)
0x180022b82  mov     rcx, [rsp+98h+pv]; pv
0x180022b87  test    al, al
0x180022b89  jz      loc_180022E57
0x180022b8f  cmp     [rcx+18h], esi
0x180022b92  jz      loc_180022E57
0x180022b98  mov     [rsp+98h+arg_10], 103Bh
0x180022ba3  lea     r8, [rsp+98h+arg_10]; unsigned int *
0x180022bab  mov     edx, edi; unsigned int
0x180022bad  lea     rcx, [rsp+98h+var_40]; this
0x180022bb2  call    ?RemoveAttributesByType@IASRequest@IASTL@@QEAAXKPEAK@Z; IASTL::IASRequest::RemoveAttributesByType(ulong,ulong *)
0x180022bb7  lea     rcx, [rbx+58h]; this
0x180022bbb  mov     rdx, [rsp+98h+var_38]; struct IAttributesRaw *
0x180022bc0  call    ?store@IASAttribute@IASTL@@QEBAXPEAUIAttributesRaw@@@Z; IASTL::IASAttribute::store(IAttributesRaw *)
0x180022bc5  lea     r9d, [rsi+6]
0x180022bc9  mov     r8d, 1047h
0x180022bcf  mov     rdx, [rsp+98h+var_38]
0x180022bd4  lea     rcx, [rsp+98h+pv]
0x180022bd9  call    ?load@IASAttribute@IASTL@@QEAA_NPEAUIAttributesRaw@@KW4IASTYPEENUM@@@Z; IASTL::IASAttribute::load(IAttributesRaw *,ulong,IASTYPEENUM)
0x180022bde  test    al, al
0x180022be0  jnz     short loc_180022C18
0x180022be2  mov     rdx, r15
0x180022be5  mov     rcx, rbx
0x180022be8  call    ?onSyncRequest@NameMapper@@MEAA?AW4_IASREQUESTSTATUS@@PEAUIRequest@@@Z; NameMapper::onSyncRequest(IRequest *)
0x180022bed  mov     ebx, eax
0x180022bef  mov     rcx, [rsp+98h+pv]; pv
0x180022bf4  test    rcx, rcx
0x180022bf7  jz      short loc_180022BFF
0x180022bf9  call    IASAttributeRelease
0x180022bfe  nop
0x180022bff  mov     rcx, [rsp+98h+var_38]
0x180022c04  mov     rdx, [rcx]
0x180022c07  mov     rax, [rdx+10h]
0x180022c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c10  nop
0x180022c11  mov     eax, ebx
0x180022c13  jmp     loc_180022ED2
0x180022c18  lea     rdx, [rsp+98h+StringSid]; StringSid
0x180022c1d  mov     rdi, [rsp+98h+pv]
0x180022c22  mov     rcx, [rdi+20h]; Sid
0x180022c26  call    cs:__imp_ConvertSidToStringSidW
0x180022c2c  test    eax, eax
0x180022c2e  jnz     short loc_180022C8C
0x180022c30  mov     rax, cs:WPP_GLOBAL_Control
0x180022c37  cmp     rax, r13
0x180022c3a  jz      short loc_180022C82
0x180022c3c  cmp     byte ptr [rax+19h], 2
0x180022c40  jb      short loc_180022C82
0x180022c42  test    byte ptr [rax+1Ch], 4
0x180022c46  jz      short loc_180022C82
0x180022c48  call    cs:__imp_GetLastError
0x180022c4e  mov     edx, eax
0x180022c50  lea     rcx, aErrorConvertsi; "Error ConvertSidToStringSid failed %x"
0x180022c57  call    WppDbgPrint
0x180022c5c  call    cs:__imp_GetLastError
0x180022c62  mov     edx, 0Bh
0x180022c67  mov     dword ptr [rsp+98h+var_78], eax
0x180022c6b  lea     r8, WPP_73a3aabcfd463fffdec8169cd7ccfd67_Traceguids
0x180022c72  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c79  mov     rcx, [rcx+10h]
0x180022c7d  call    WPP_SF_sd
0x180022c82  mov     ecx, 8; int
0x180022c87  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180022c8c  mov     [rsp+98h+var_50], rsi
0x180022c91  mov     r9d, 5
0x180022c97  mov     r8d, 1049h
0x180022c9d  mov     rdx, [rsp+98h+var_38]
0x180022ca2  lea     rcx, [rsp+98h+var_50]
0x180022ca7  call    ?load@IASAttribute@IASTL@@QEAA_NPEAUIAttributesRaw@@KW4IASTYPEENUM@@@Z; IASTL::IASAttribute::load(IAttributesRaw *,ulong,IASTYPEENUM)
0x180022cac  lea     rcx, [rsp+98h+var_68]; this
0x180022cb1  call    ??0IASAttribute@IASTL@@QEAA@_N@Z; IASTL::IASAttribute::IASAttribute(bool)
0x180022cb6  nop
0x180022cb7  mov     rax, [rsp+98h+var_68]
0x180022cbc  mov     dword ptr [rax+8], 1021h
0x180022cc3  mov     rax, cs:WPP_GLOBAL_Control
0x180022cca  cmp     rax, r13
0x180022ccd  jz      short loc_180022D12
0x180022ccf  cmp     byte ptr [rax+19h], 4
0x180022cd3  jb      short loc_180022D12
0x180022cd5  test    byte ptr [rax+1Ch], 4
0x180022cd9  jz      short loc_180022D12
0x180022cdb  mov     rdx, [rsp+98h+StringSid]
0x180022ce0  lea     rcx, aSidReceivedS; "SID received %S"
0x180022ce7  call    WppDbgPrint
0x180022cec  mov     edx, 0Ch
0x180022cf1  mov     rax, [rsp+98h+StringSid]
0x180022cf6  mov     [rsp+98h+var_78], rax
0x180022cfb  lea     r8, WPP_73a3aabcfd463fffdec8169cd7ccfd67_Traceguids
0x180022d02  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d09  mov     rcx, [rcx+10h]
0x180022d0d  call    WPP_SF_sS
0x180022d12  mov     rbx, [rsp+98h+var_50]
0x180022d17  test    rbx, rbx
0x180022d1a  jz      short loc_180022D22
0x180022d1c  mov     rax, [rbx+20h]
0x180022d20  jmp     short loc_180022D25
0x180022d22  mov     rax, rsi
0x180022d25  mov     [rsp+98h+var_78], rax; unsigned __int16 *
0x180022d2a  mov     r9d, 0Bh; enum DS_NAME_FORMAT
0x180022d30  lea     r8, [rsp+98h+var_68]; struct IASTL::IASAttribute *
0x180022d35  mov     rdx, [rsp+98h+StringSid]; unsigned __int16 *
0x180022d3a  call    ?mapName@NameMapper@@IEAAXPEBGAEAVIASAttribute@IASTL@@W4DS_NAME_FORMAT@@0@Z; NameMapper::mapName(ushort const *,IASTL::IASAttribute &,DS_NAME_FORMAT,ushort const *)
0x180022d3f  mov     rax, [rsp+98h+var_68]
0x180022d44  mov     rcx, [rax+20h]; Str
0x180022d48  test    rcx, rcx
0x180022d4b  jz      short loc_180022D7B
0x180022d4d  mov     edx, 5Ch ; '\'; Ch
0x180022d52  call    cs:__imp_wcschr
0x180022d58  mov     r13, rax
0x180022d5b  mov     [rax], si
0x180022d5e  mov     rcx, [rsp+98h+var_68]
0x180022d63  mov     rcx, [rcx+20h]; String
0x180022d67  call    cs:__imp__wcsupr
0x180022d6d  mov     word ptr [r13+0], 5Ch ; '\'
0x180022d74  lea     r13, WPP_GLOBAL_Control
0x180022d7b  mov     rdx, [rsp+98h+var_38]; struct IAttributesRaw *
0x180022d80  lea     rcx, [rsp+98h+var_68]; this
0x180022d85  call    ?store@IASAttribute@IASTL@@QEBAXPEAUIAttributesRaw@@@Z; IASTL::IASAttribute::store(IAttributesRaw *)
0x180022d8a  mov     r8, [rsp+98h+var_68]
0x180022d8f  mov     r8, [r8+20h]; unsigned __int16 *
0x180022d93  mov     edx, 2; enum DS_NAME_FORMAT
0x180022d98  mov     rcx, [rsp+98h+var_38]; struct IAttributesRaw *
0x180022d9d  call    ?IASStoreFQUserName@@YAJPEAUIAttributesRaw@@W4DS_NAME_FORMAT@@PEBG@Z; IASStoreFQUserName(IAttributesRaw *,DS_NAME_FORMAT,ushort const *)
0x180022da2  mov     rax, cs:WPP_GLOBAL_Control
0x180022da9  cmp     rax, r13
0x180022dac  jz      short loc_180022DF9
0x180022dae  cmp     byte ptr [rax+19h], 4
0x180022db2  jb      short loc_180022DF9
0x180022db4  test    byte ptr [rax+1Ch], 4
0x180022db8  jz      short loc_180022DF9
0x180022dba  mov     rdx, [rsp+98h+var_68]
0x180022dbf  mov     rdx, [rdx+20h]
0x180022dc3  lea     rcx, aSamAccountName; "SAM-Account-Name is \"%S\"."
0x180022dca  call    WppDbgPrint
0x180022dcf  mov     edx, 0Dh
0x180022dd4  mov     rax, [rsp+98h+var_68]
0x180022dd9  mov     rcx, [rax+20h]
0x180022ddd  mov     [rsp+98h+var_78], rcx
0x180022de2  lea     r8, WPP_73a3aabcfd463fffdec8169cd7ccfd67_Traceguids
0x180022de9  mov     rcx, cs:WPP_GLOBAL_Control
0x180022df0  mov     rcx, [rcx+10h]
0x180022df4  call    WPP_SF_sS
0x180022df9  mov     [rsp+98h+arg_18], 1047h
0x180022e04  lea     r8, [rsp+98h+arg_18]; unsigned int *
0x180022e0c  mov     edx, 1; unsigned int
0x180022e11  lea     rcx, [rsp+98h+var_40]; this
0x180022e16  call    ?RemoveAttributesByType@IASRequest@IASTL@@QEAAXKPEAK@Z; IASTL::IASRequest::RemoveAttributesByType(ulong,ulong *)
0x180022e1b  nop
0x180022e1c  mov     rcx, [rsp+98h+var_68]; pv
0x180022e21  test    rcx, rcx
0x180022e24  jz      short loc_180022E2C
0x180022e26  call    IASAttributeRelease
0x180022e2b  nop
0x180022e2c  test    rbx, rbx
0x180022e2f  jz      short loc_180022E3A
0x180022e31  mov     rcx, rbx; pv
0x180022e34  call    IASAttributeRelease
0x180022e39  nop
0x180022e3a  mov     rcx, rdi; pv
0x180022e3d  call    IASAttributeRelease
0x180022e42  nop
0x180022e43  mov     rcx, [rsp+98h+var_38]
0x180022e48  mov     rax, [rcx]
0x180022e4b  mov     rax, [rax+10h]
0x180022e4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e54  nop
0x180022e55  jmp     short loc_180022E8D
0x180022e57  test    rcx, rcx
0x180022e5a  jz      short loc_180022E62
0x180022e5c  call    IASAttributeRelease
0x180022e61  nop
0x180022e62  mov     rcx, [rsp+98h+var_38]
0x180022e67  mov     rax, [rcx]
0x180022e6a  mov     rax, [rax+10h]
0x180022e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e73  nop
0x180022e74  mov     eax, 2
0x180022e79  jmp     short loc_180022ED2
0x180022e7b  jmp     short $+2
0x180022e7d  mov     r12d, [rsp+98h+arg_10]
0x180022e85  mov     r15, [rsp+98h+arg_8]
0x180022e8d  mov     rcx, [rsp+98h+StringSid]; hMem
0x180022e92  test    rcx, rcx
0x180022e95  jz      short loc_180022E9D
0x180022e97  call    cs:__imp_LocalFree
0x180022e9d  test    r12d, r12d
0x180022ea0  jz      short loc_180022ECD
0x180022ea2  cmp     r12d, 0FFFFh
0x180022ea9  jge     short loc_180022ECD
0x180022eab  mov     rax, [r15]
0x180022eae  mov     edx, r12d
0x180022eb1  mov     rcx, r15
0x180022eb4  mov     rax, [rax+80h]
0x180022ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ec0  mov     edx, r12d
0x180022ec3  mov     rcx, r15
0x180022ec6  call    ?IASProcessFailure@@YA?AW4_IASREQUESTSTATUS@@PEAUIRequest@@J@Z; IASProcessFailure(IRequest *,long)
0x180022ecb  jmp     short loc_180022ED2
0x180022ecd  mov     eax, 2
0x180022ed2  mov     rbx, [rsp+98h+arg_0]
0x180022eda  add     rsp, 70h
0x180022ede  pop     r15
0x180022ee0  pop     r13
0x180022ee2  pop     r12
0x180022ee4  pop     rdi
0x180022ee5  pop     rsi
0x180022ee6  retn
```
