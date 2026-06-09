# AuthorizationHost::onSyncRequest(IRequest *)

- ea: `0x180013ce0`
- end: `0x180013ead`
- name: `?onSyncRequest@AuthorizationHost@@MEAA?AW4_IASREQUESTSTATUS@@PEAUIRequest@@@Z`
- size: `461`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000acf4`
- `0x18000b24c`
- `0x18000ba5c`
- `0x18000c4a4`
- `0x18000dfa4`
- `0x1800133bc`
- `0x180013ce0`
- `0x180013ff4`
- `0x180014098`
- `0x1800254a0`
- `0x18002e010`

## import_xrefs

- `iasrad!?radiusFromIAS@VSAFilter@@QEBAJPEAUIAttributesRaw@@H@Z` at `0x180013e49`
- `iasrad!?radiusFromIAS@VSAFilter@@QEBAJPEAUIAttributesRaw@@H@Z` at `0x180013e49`
- `iasrad!?radiusToIAS@VSAFilter@@QEBAJPEAUIAttributesRaw@@@Z` at `0x180013e65`
- `iasrad!?radiusToIAS@VSAFilter@@QEBAJPEAUIAttributesRaw@@@Z` at `0x180013e65`

## string_xrefs

- `0x180013df4`: `No AUTHORIZATION extensions, continuing`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall AuthorizationHost::onSyncRequest(_BYTE *a1, struct IRequest *a2)
{
  void *v4; // rbx
  char v5; // al
  bool v6; // di
  bool v7; // si
  _BYTE v9[8]; // [rsp+28h] [rbp-30h] BYREF
  struct IAttributesRaw *v10; // [rsp+30h] [rbp-28h]
  LPVOID pv; // [rsp+70h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Entering AuthorizationHost stage");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids, "NPSSVC");
  }
  IASTL::IASRequest::IASRequest((IASTL::IASRequest *)v9, a2);
  v4 = 0;
  pv = 0;
  v6 = 0;
  if ( (unsigned int)IASTL::IASRequest::get_Response(v9) - 1 <= 1 )
  {
    v5 = IASTL::IASAttribute::load(&pv, v10, 8113, 1);
    v4 = pv;
    if ( v5 )
    {
      if ( *((_DWORD *)pv + 6) )
        v6 = 1;
    }
  }
  if ( v4 )
    IASAttributeRelease(v4);
  if ( v6 )
  {
    v7 = (unsigned int)IASTL::IASRequest::get_Response(v9) == 1;
    AuthorizationHost::preProcess((struct IASTL::IASRequest *)v9);
  }
  else
  {
    v7 = 0;
  }
  if ( a1[96] )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("No AUTHORIZATION extensions, continuing");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids, "NPSSVC");
    }
  }
  else
  {
    VSAFilter::radiusFromIAS((VSAFilter *)(a1 + 80), v10, 0);
    BaseCampHostBase::ProcessExtensions((BaseCampHostBase *)a1, (struct IASTL::IASRequest *)v9);
    VSAFilter::radiusToIAS((VSAFilter *)(a1 + 80), v10);
    if ( v6 )
      AuthorizationHost::postProcess((struct IASTL::IASRequest *)v9, v7);
  }
  (*(void (__fastcall **)(struct IAttributesRaw *))(*(_QWORD *)v10 + 16LL))(v10);
  return 1;
}

```

## disassembly

```asm
0x180013ce0  mov     [rsp+arg_0], rbx
0x180013ce5  mov     [rsp+arg_18], rsi
0x180013cea  mov     [rsp+arg_8], rdx
0x180013cef  push    rdi
0x180013cf0  push    r14
0x180013cf2  push    r15
0x180013cf4  sub     rsp, 40h
0x180013cf8  mov     rbx, rdx
0x180013cfb  mov     r14, rcx
0x180013cfe  lea     r15, WPP_GLOBAL_Control
0x180013d05  mov     rax, cs:WPP_GLOBAL_Control
0x180013d0c  cmp     rax, r15
0x180013d0f  jz      short loc_180013D4D
0x180013d11  cmp     byte ptr [rax+19h], 4
0x180013d15  jb      short loc_180013D4D
0x180013d17  test    byte ptr [rax+1Ch], 4
0x180013d1b  jz      short loc_180013D4D
0x180013d1d  lea     rcx, aEnteringAuthor; "Entering AuthorizationHost stage"
0x180013d24  call    WppDbgPrint
0x180013d29  mov     edx, 24h ; '$'
0x180013d2e  lea     r9, aNpssvc; "NPSSVC"
0x180013d35  lea     r8, WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids
0x180013d3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d43  mov     rcx, [rcx+10h]
0x180013d47  call    WPP_SF_s
0x180013d4c  nop
0x180013d4d  mov     rdx, rbx; struct IRequest *
0x180013d50  lea     rcx, [rsp+58h+var_30]; this
0x180013d55  call    ??0IASRequest@IASTL@@QEAA@PEAUIRequest@@@Z; IASTL::IASRequest::IASRequest(IRequest *)
0x180013d5a  nop
0x180013d5b  xor     ebx, ebx
0x180013d5d  mov     [rsp+58h+pv], rbx
0x180013d62  lea     rcx, [rsp+58h+var_30]
0x180013d67  call    ?get_Response@IASRequest@IASTL@@QEBA?AW4_IASRESPONSE@@XZ; IASTL::IASRequest::get_Response(void)
0x180013d6c  dec     eax
0x180013d6e  cmp     eax, 1
0x180013d71  ja      short loc_180013DA0
0x180013d73  lea     r9d, [rbx+1]
0x180013d77  mov     r8d, 1FB1h
0x180013d7d  mov     rdx, [rsp+58h+var_28]
0x180013d82  lea     rcx, [rsp+58h+pv]
0x180013d87  call    ?load@IASAttribute@IASTL@@QEAA_NPEAUIAttributesRaw@@KW4IASTYPEENUM@@@Z; IASTL::IASAttribute::load(IAttributesRaw *,ulong,IASTYPEENUM)
0x180013d8c  mov     rbx, [rsp+58h+pv]
0x180013d91  test    al, al
0x180013d93  jz      short loc_180013DA0
0x180013d95  cmp     dword ptr [rbx+18h], 0
0x180013d99  jz      short loc_180013DA0
0x180013d9b  mov     dil, 1
0x180013d9e  jmp     short loc_180013DA3
0x180013da0  xor     dil, dil
0x180013da3  test    rbx, rbx
0x180013da6  jz      short loc_180013DB0
0x180013da8  mov     rcx, rbx; pv
0x180013dab  call    IASAttributeRelease
0x180013db0  test    dil, dil
0x180013db3  jz      short loc_180013DD2
0x180013db5  lea     rcx, [rsp+58h+var_30]
0x180013dba  call    ?get_Response@IASRequest@IASTL@@QEBA?AW4_IASRESPONSE@@XZ; IASTL::IASRequest::get_Response(void)
0x180013dbf  cmp     eax, 1
0x180013dc2  setz    sil
0x180013dc6  lea     rcx, [rsp+58h+var_30]; struct IASTL::IASRequest *
0x180013dcb  call    ?preProcess@AuthorizationHost@@CAXAEAVIASRequest@IASTL@@@Z; AuthorizationHost::preProcess(IASTL::IASRequest &)
0x180013dd0  jmp     short loc_180013DD5
0x180013dd2  xor     sil, sil
0x180013dd5  cmp     byte ptr [r14+60h], 0
0x180013dda  jz      short loc_180013E3D
0x180013ddc  mov     rax, cs:WPP_GLOBAL_Control
0x180013de3  cmp     rax, r15
0x180013de6  jz      short loc_180013E24
0x180013de8  cmp     byte ptr [rax+19h], 4
0x180013dec  jb      short loc_180013E24
0x180013dee  test    byte ptr [rax+1Ch], 4
0x180013df2  jz      short loc_180013E24
0x180013df4  lea     rcx, aNoAuthorizatio; "No AUTHORIZATION extensions, continuing"
0x180013dfb  call    WppDbgPrint
0x180013e00  mov     edx, 25h ; '%'
0x180013e05  lea     r9, aNpssvc; "NPSSVC"
0x180013e0c  lea     r8, WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids
0x180013e13  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e1a  mov     rcx, [rcx+10h]
0x180013e1e  call    WPP_SF_s
0x180013e23  nop
0x180013e24  mov     rcx, [rsp+58h+var_28]
0x180013e29  mov     rdx, [rcx]
0x180013e2c  mov     rax, [rdx+10h]
0x180013e30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e35  nop
0x180013e36  mov     eax, 1
0x180013e3b  jmp     short loc_180013E99
0x180013e3d  xor     r8d, r8d
0x180013e40  mov     rdx, [rsp+58h+var_28]
0x180013e45  lea     rcx, [r14+50h]
0x180013e49  call    cs:__imp_?radiusFromIAS@VSAFilter@@QEBAJPEAUIAttributesRaw@@H@Z; VSAFilter::radiusFromIAS(IAttributesRaw *,int)
0x180013e4f  lea     rdx, [rsp+58h+var_30]; struct IASTL::IASRequest *
0x180013e54  mov     rcx, r14; this
0x180013e57  call    ?ProcessExtensions@BaseCampHostBase@@IEAAXAEAVIASRequest@IASTL@@@Z; BaseCampHostBase::ProcessExtensions(IASTL::IASRequest &)
0x180013e5c  mov     rdx, [rsp+58h+var_28]
0x180013e61  lea     rcx, [r14+50h]
0x180013e65  call    cs:__imp_?radiusToIAS@VSAFilter@@QEBAJPEAUIAttributesRaw@@@Z; VSAFilter::radiusToIAS(IAttributesRaw *)
0x180013e6b  test    dil, dil
0x180013e6e  jz      short loc_180013E7E
0x180013e70  mov     dl, sil; bool
0x180013e73  lea     rcx, [rsp+58h+var_30]; struct IASTL::IASRequest *
0x180013e78  call    ?postProcess@AuthorizationHost@@CAXAEAVIASRequest@IASTL@@_N@Z; AuthorizationHost::postProcess(IASTL::IASRequest &,bool)
0x180013e7d  nop
0x180013e7e  mov     rcx, [rsp+58h+var_28]
0x180013e83  mov     rax, [rcx]
0x180013e86  mov     rax, [rax+10h]
0x180013e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e8f  nop
0x180013e90  jmp     short loc_180013E94
0x180013e92  jmp     short $+2
0x180013e94  mov     eax, 1
0x180013e99  mov     rbx, [rsp+58h+arg_0]
0x180013e9e  mov     rsi, [rsp+58h+arg_18]
0x180013ea3  add     rsp, 40h
0x180013ea7  pop     r15
0x180013ea9  pop     r14
0x180013eab  pop     rdi
0x180013eac  retn
```
