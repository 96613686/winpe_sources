# AccountValidation::doDownlevel(IASTL::IASRequest &,ushort const *,ushort const *,bool,bool)

- ea: `0x18000dbc0`
- end: `0x18000df34`
- name: `?doDownlevel@AccountValidation@@CAXAEAVIASRequest@IASTL@@PEBG1_N2@Z`
- size: `884`
- prototype: `void __usercall(struct IASTL::IASRequest *@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, bool@<r9b>, bool)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d630`

## callees

- `0x18000acf4`
- `0x18000b484`
- `0x18000b82c`
- `0x18000c28c`
- `0x18000c4a4`
- `0x18000c500`
- `0x18000d55c`
- `0x18000dbc0`
- `0x18000e7d4`
- `0x18000e8a4`
- `0x18000ea60`
- `0x180016884`
- `0x1800254a0`
- `0x1800282e4`
- `0x18002944c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dca1`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall AccountValidation::doDownlevel(
        struct IAttributesRaw **a1,
        wchar_t *a2,
        const unsigned __int16 *a3,
        char a4,
        bool a5)
{
  bool v8; // dl
  _DWORD *v9; // rdi
  _DWORD *v10; // rsi
  bool v11; // dl
  unsigned int v12; // r15d
  int v13; // r15d
  const char *v14; // rbx
  void *v15; // rcx
  _DWORD *v16; // rbx
  unsigned int v17; // eax
  int v18; // [rsp+50h] [rbp-21h] BYREF
  void *v19; // [rsp+58h] [rbp-19h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-11h] BYREF
  LPVOID v21; // [rsp+68h] [rbp-9h] BYREF
  LPVOID v22[10]; // [rsp+70h] [rbp-1h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Using downlevel APIs to validate account.");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_4efc2f519167317fc72c7fedb48c5519_Traceguids, "NPSSVC");
  }
  IASTL::IASAttribute::IASAttribute((IASTL::IASAttribute *)v22, (bool)a2);
  IASTL::IASAttribute::IASAttribute((IASTL::IASAttribute *)&v21, v8);
  v9 = v22[0];
  *((_DWORD *)v22[0] + 4) = 6;
  v10 = v21;
  *((_DWORD *)v21 + 4) = 6;
  v10[6] = 0;
  pv = 0;
  v18 = 1;
  v12 = IASGetGroupsForUser(
          (__int64)a3,
          a2,
          (__int64 (*)(void))CoTaskMemAlloc,
          (int)v9 + 32,
          (__int64)(v9 + 6),
          (__int64)&pv,
          &v18,
          (_QWORD *)v10 + 4,
          v10 + 6);
  if ( v10[6] && *((_QWORD *)v10 + 4) && !IASPeekAttribute(a1[1], (unsigned int)a5 + 8161, 6) )
  {
    v10[2] = a5 + 8161;
    v10[4] = 6;
    IASTL::IASAttribute::store((IASTL::IASAttribute *)&v21, a1[1]);
  }
  if ( v12 )
  {
    if ( a4 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("Could not validate windows account %S\\%S. Continuing without failing the request.");
        WPP_SF_sSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2, (__int64)a3);
      }
      IASTL::IASAttribute::IASAttribute((IASTL::IASAttribute *)&pv, v11);
      v16 = pv;
      *((_DWORD *)pv + 2) = 8167;
      v16[4] = 2;
      v16[6] = IASMapWin32Error(v12, 5);
      IASTL::IASAttribute::store((IASTL::IASAttribute *)&pv, a1[1]);
      v15 = v16;
      goto LABEL_28;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("IASGetGroupsForUser failed with error: %d");
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_4efc2f519167317fc72c7fedb48c5519_Traceguids);
    }
    v17 = IASMapWin32Error(v12, 6);
    IASProcessFailure(*a1, v17);
  }
  else
  {
    v19 = 0;
    v13 = v18;
    if ( v18 || !IASTL::IASAttribute::load((IASTL::IASAttribute *)&v19, a1[1], 0x1FB6u) )
    {
      if ( !IASTL::IASAttribute::load((IASTL::IASAttribute *)&v19, a1[1], 0x1FB7u) )
        InsertInternalTimeout((struct IASTL::IASRequest *)a1, (const union _LARGE_INTEGER *)&pv);
      v9[2] = (v13 != 0) + 8118;
      v9[4] = 6;
      v9[1] |= 0x30000u;
      IASTL::IASAttribute::store((IASTL::IASAttribute *)v22, a1[1]);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v14 = "user";
        WppDbgPrint("Successfully validated windows %s account %S\\%S.");
        if ( !v13 )
          v14 = "machine";
        WPP_SF_ssSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v14, (__int64)a2, (__int64)a3);
      }
    }
    v15 = v19;
    if ( v19 )
LABEL_28:
      IASAttributeRelease(v15);
  }
  IASAttributeRelease(v10);
  if ( v9 )
    IASAttributeRelease(v9);
}

```

## disassembly

```asm
0x18000dbc0  mov     [rsp-8+arg_18], r9b
0x18000dbc5  push    rbp
0x18000dbc6  push    rbx
0x18000dbc7  push    rsi
0x18000dbc8  push    rdi
0x18000dbc9  push    r12
0x18000dbcb  push    r13
0x18000dbcd  push    r14
0x18000dbcf  push    r15
0x18000dbd1  lea     rbp, [rsp-17h]
0x18000dbd6  sub     rsp, 88h
0x18000dbdd  mov     r12, r8
0x18000dbe0  mov     r13, rdx
0x18000dbe3  mov     r14, rcx
0x18000dbe6  lea     rcx, WPP_GLOBAL_Control
0x18000dbed  mov     rax, cs:WPP_GLOBAL_Control
0x18000dbf4  cmp     rax, rcx
0x18000dbf7  jz      short loc_18000DC34
0x18000dbf9  cmp     byte ptr [rax+19h], 4
0x18000dbfd  jb      short loc_18000DC34
0x18000dbff  test    byte ptr [rax+1Ch], 4
0x18000dc03  jz      short loc_18000DC34
0x18000dc05  lea     rcx, aUsingDownlevel; "Using downlevel APIs to validate accoun"...
0x18000dc0c  call    WppDbgPrint
0x18000dc11  mov     edx, 0Bh
0x18000dc16  lea     r9, aNpssvc; "NPSSVC"
0x18000dc1d  lea     r8, WPP_4efc2f519167317fc72c7fedb48c5519_Traceguids
0x18000dc24  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc2b  mov     rcx, [rcx+10h]
0x18000dc2f  call    WPP_SF_s
0x18000dc34  lea     rcx, [rbp+4Fh+var_50]; this
0x18000dc38  call    ??0IASAttribute@IASTL@@QEAA@_N@Z; IASTL::IASAttribute::IASAttribute(bool)
0x18000dc3d  nop
0x18000dc3e  lea     rcx, [rbp+4Fh+var_58]; this
0x18000dc42  call    ??0IASAttribute@IASTL@@QEAA@_N@Z; IASTL::IASAttribute::IASAttribute(bool)
0x18000dc47  nop
0x18000dc48  mov     rdi, [rbp+4Fh+var_50]
0x18000dc4c  mov     eax, 6
0x18000dc51  mov     [rdi+10h], eax
0x18000dc54  mov     rsi, [rbp+4Fh+var_58]
0x18000dc58  mov     [rsi+10h], eax
0x18000dc5b  lea     rbx, [rsi+18h]
0x18000dc5f  mov     dword ptr [rbx], 0
0x18000dc65  mov     [rbp+4Fh+pv], 0
0x18000dc6d  mov     [rbp+4Fh+var_70], 1
0x18000dc74  lea     rcx, [rdi+18h]
0x18000dc78  lea     rax, [rbx+8]
0x18000dc7c  lea     r9, [rcx+8]
0x18000dc80  mov     [rsp+0C0h+var_80], rbx
0x18000dc85  mov     [rsp+0C0h+var_88], rax
0x18000dc8a  lea     rax, [rbp+4Fh+var_70]
0x18000dc8e  mov     [rsp+0C0h+var_90], rax
0x18000dc93  lea     rax, [rbp+4Fh+pv]
0x18000dc97  mov     [rsp+0C0h+var_98], rax
0x18000dc9c  mov     [rsp+0C0h+var_A0], rcx
0x18000dca1  mov     r8, cs:__imp_CoTaskMemAlloc
0x18000dca8  mov     rdx, r13
0x18000dcab  mov     rcx, r12
0x18000dcae  call    IASGetGroupsForUser
0x18000dcb3  mov     r15d, eax
0x18000dcb6  cmp     dword ptr [rbx], 0
0x18000dcb9  jbe     short loc_18000DCF9
0x18000dcbb  cmp     qword ptr [rsi+20h], 0
0x18000dcc0  jz      short loc_18000DCF9
0x18000dcc2  movzx   ebx, [rbp+4Fh+arg_20]
0x18000dcc6  add     ebx, 1FE1h
0x18000dccc  mov     r8d, 6
0x18000dcd2  mov     edx, ebx
0x18000dcd4  mov     rcx, [r14+8]
0x18000dcd8  call    ?IASPeekAttribute@@YAPEAU_IASATTRIBUTE@@PEAUIAttributesRaw@@KW4IASTYPEENUM@@@Z; IASPeekAttribute(IAttributesRaw *,ulong,IASTYPEENUM)
0x18000dcdd  test    rax, rax
0x18000dce0  jnz     short loc_18000DCF9
0x18000dce2  mov     [rsi+8], ebx
0x18000dce5  mov     dword ptr [rsi+10h], 6
0x18000dcec  mov     rdx, [r14+8]; struct IAttributesRaw *
0x18000dcf0  lea     rcx, [rbp+4Fh+var_58]; this
0x18000dcf4  call    ?store@IASAttribute@IASTL@@QEBAXPEAUIAttributesRaw@@@Z; IASTL::IASAttribute::store(IAttributesRaw *)
0x18000dcf9  test    r15d, r15d
0x18000dcfc  jnz     loc_18000DDFE
0x18000dd02  mov     [rbp+4Fh+var_68], 0
0x18000dd0a  mov     ebx, 1FB6h
0x18000dd0f  mov     r15d, [rbp+4Fh+var_70]
0x18000dd13  test    r15d, r15d
0x18000dd16  jnz     short loc_18000DD30
0x18000dd18  mov     r8d, ebx; unsigned int
0x18000dd1b  mov     rdx, [r14+8]; struct IAttributesRaw *
0x18000dd1f  lea     rcx, [rbp+4Fh+var_68]; this
0x18000dd23  call    ?load@IASAttribute@IASTL@@QEAA_NPEAUIAttributesRaw@@K@Z; IASTL::IASAttribute::load(IAttributesRaw *,ulong)
0x18000dd28  test    al, al
0x18000dd2a  jnz     loc_18000DDEC
0x18000dd30  mov     r8d, 1FB7h; unsigned int
0x18000dd36  mov     rdx, [r14+8]; struct IAttributesRaw *
0x18000dd3a  lea     rcx, [rbp+4Fh+var_68]; this
0x18000dd3e  call    ?load@IASAttribute@IASTL@@QEAA_NPEAUIAttributesRaw@@K@Z; IASTL::IASAttribute::load(IAttributesRaw *,ulong)
0x18000dd43  test    al, al
0x18000dd45  jnz     short loc_18000DD53
0x18000dd47  lea     rdx, [rbp+4Fh+pv]; union _LARGE_INTEGER *
0x18000dd4b  mov     rcx, r14; struct IASTL::IASRequest *
0x18000dd4e  call    ?InsertInternalTimeout@@YAXAEAVIASRequest@IASTL@@AEBT_LARGE_INTEGER@@@Z; InsertInternalTimeout(IASTL::IASRequest &,_LARGE_INTEGER const &)
0x18000dd53  mov     eax, r15d
0x18000dd56  neg     eax
0x18000dd58  sbb     ecx, ecx
0x18000dd5a  neg     ecx
0x18000dd5c  add     ecx, ebx
0x18000dd5e  mov     [rdi+8], ecx
0x18000dd61  mov     dword ptr [rdi+10h], 6
0x18000dd68  or      dword ptr [rdi+4], 30000h
0x18000dd6f  mov     rdx, [r14+8]; struct IAttributesRaw *
0x18000dd73  lea     rcx, [rbp+4Fh+var_50]; this
0x18000dd77  call    ?store@IASAttribute@IASTL@@QEBAXPEAUIAttributesRaw@@@Z; IASTL::IASAttribute::store(IAttributesRaw *)
0x18000dd7c  mov     rax, cs:WPP_GLOBAL_Control
0x18000dd83  lea     rcx, WPP_GLOBAL_Control
0x18000dd8a  cmp     rax, rcx
0x18000dd8d  jz      short loc_18000DDEC
0x18000dd8f  cmp     byte ptr [rax+19h], 4
0x18000dd93  jb      short loc_18000DDEC
0x18000dd95  test    byte ptr [rax+1Ch], 4
0x18000dd99  jz      short loc_18000DDEC
0x18000dd9b  lea     rbx, aUser; "user"
0x18000dda2  mov     rdx, rbx
0x18000dda5  lea     r14, aMachine; "machine"
0x18000ddac  test    r15d, r15d
0x18000ddaf  cmovz   rdx, r14
0x18000ddb3  mov     r9, r12
0x18000ddb6  mov     r8, r13
0x18000ddb9  lea     rcx, aSuccessfullyVa; "Successfully validated windows %s accou"...
0x18000ddc0  call    WppDbgPrint
0x18000ddc5  test    r15d, r15d
0x18000ddc8  cmovz   rbx, r14
0x18000ddcc  mov     [rsp+0C0h+var_90], r12; __int64
0x18000ddd1  mov     [rsp+0C0h+var_98], r13; __int64
0x18000ddd6  mov     [rsp+0C0h+var_A0], rbx; __int64
0x18000dddb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dde2  mov     rcx, [rcx+10h]; LoggerHandle
0x18000dde6  call    WPP_SF_ssSS
0x18000ddeb  nop
0x18000ddec  mov     rcx, [rbp+4Fh+var_68]
0x18000ddf0  test    rcx, rcx
0x18000ddf3  jz      loc_18000DF0A
0x18000ddf9  jmp     loc_18000DE9C
0x18000ddfe  cmp     [rbp+4Fh+arg_18], 0
0x18000de02  jz      loc_18000DEA3
0x18000de08  mov     rax, cs:WPP_GLOBAL_Control
0x18000de0f  lea     rcx, WPP_GLOBAL_Control
0x18000de16  cmp     rax, rcx
0x18000de19  jz      short loc_18000DE5F
0x18000de1b  cmp     byte ptr [rax+19h], 2
0x18000de1f  jb      short loc_18000DE5F
0x18000de21  test    byte ptr [rax+1Ch], 4
0x18000de25  jz      short loc_18000DE5F
0x18000de27  mov     r8, r12
0x18000de2a  mov     rdx, r13
0x18000de2d  lea     rcx, aCouldNotValida; "Could not validate windows account %S\\"...
0x18000de34  call    WppDbgPrint
0x18000de39  mov     edx, 0Dh
0x18000de3e  mov     [rsp+0C0h+var_98], r12; __int64
0x18000de43  mov     [rsp+0C0h+var_A0], r13; __int64
0x18000de48  lea     r8, WPP_4efc2f519167317fc72c7fedb48c5519_Traceguids
0x18000de4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de56  mov     rcx, [rcx+10h]; LoggerHandle
0x18000de5a  call    WPP_SF_sSS
0x18000de5f  lea     rcx, [rbp+4Fh+pv]; this
0x18000de63  call    ??0IASAttribute@IASTL@@QEAA@_N@Z; IASTL::IASAttribute::IASAttribute(bool)
0x18000de68  nop
0x18000de69  mov     rbx, [rbp+4Fh+pv]
0x18000de6d  mov     dword ptr [rbx+8], 1FE7h
0x18000de74  mov     dword ptr [rbx+10h], 2
0x18000de7b  mov     edx, 5
0x18000de80  mov     ecx, r15d
0x18000de83  call    IASMapWin32Error
0x18000de88  mov     [rbx+18h], eax
0x18000de8b  mov     rdx, [r14+8]; struct IAttributesRaw *
0x18000de8f  lea     rcx, [rbp+4Fh+pv]; this
0x18000de93  call    ?store@IASAttribute@IASTL@@QEBAXPEAUIAttributesRaw@@@Z; IASTL::IASAttribute::store(IAttributesRaw *)
0x18000de98  nop
0x18000de99  mov     rcx, rbx; pv
0x18000de9c  call    IASAttributeRelease
0x18000dea1  jmp     short loc_18000DF0A
0x18000dea3  mov     rax, cs:WPP_GLOBAL_Control
0x18000deaa  lea     rcx, WPP_GLOBAL_Control
0x18000deb1  cmp     rax, rcx
0x18000deb4  jz      short loc_18000DEF2
0x18000deb6  cmp     byte ptr [rax+19h], 2
0x18000deba  jb      short loc_18000DEF2
0x18000debc  test    byte ptr [rax+1Ch], 4
0x18000dec0  jz      short loc_18000DEF2
0x18000dec2  mov     edx, r15d
0x18000dec5  lea     rcx, aIasgetgroupsfo; "IASGetGroupsForUser failed with error: "...
0x18000decc  call    WppDbgPrint
0x18000ded1  mov     edx, 0Eh
0x18000ded6  mov     dword ptr [rsp+0C0h+var_A0], r15d
0x18000dedb  lea     r8, WPP_4efc2f519167317fc72c7fedb48c5519_Traceguids
0x18000dee2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dee9  mov     rcx, [rcx+10h]
0x18000deed  call    WPP_SF_sd
0x18000def2  mov     edx, 6
0x18000def7  mov     ecx, r15d
0x18000defa  call    IASMapWin32Error
0x18000deff  mov     edx, eax
0x18000df01  mov     rcx, [r14]
0x18000df04  call    ?IASProcessFailure@@YA?AW4_IASREQUESTSTATUS@@PEAUIRequest@@J@Z; IASProcessFailure(IRequest *,long)
0x18000df09  nop
0x18000df0a  mov     rcx, rsi; pv
0x18000df0d  call    IASAttributeRelease
0x18000df12  nop
0x18000df13  test    rdi, rdi
0x18000df16  jz      short loc_18000DF20
0x18000df18  mov     rcx, rdi; pv
0x18000df1b  call    IASAttributeRelease
0x18000df20  add     rsp, 88h
0x18000df27  pop     r15
0x18000df29  pop     r14
0x18000df2b  pop     r13
0x18000df2d  pop     r12
0x18000df2f  pop     rdi
0x18000df30  pop     rsi
0x18000df31  pop     rbx
0x18000df32  pop     rbp
0x18000df33  retn
```
