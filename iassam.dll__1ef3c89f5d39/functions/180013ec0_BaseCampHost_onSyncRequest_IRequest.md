# BaseCampHost::onSyncRequest(IRequest *)

- ea: `0x180013ec0`
- end: `0x180013feb`
- name: `?onSyncRequest@BaseCampHost@@MEAA?AW4_IASREQUESTSTATUS@@PEAUIRequest@@@Z`
- size: `299`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b24c`
- `0x18000c4a4`
- `0x1800133bc`
- `0x180013ec0`
- `0x1800254a0`
- `0x18002e010`

## import_xrefs

- `iasrad!?radiusFromIAS@VSAFilter@@QEBAJPEAUIAttributesRaw@@H@Z` at `0x180013f9d`
- `iasrad!?radiusFromIAS@VSAFilter@@QEBAJPEAUIAttributesRaw@@H@Z` at `0x180013f9d`
- `iasrad!?radiusToIAS@VSAFilter@@QEBAJPEAUIAttributesRaw@@@Z` at `0x180013fb9`
- `iasrad!?radiusToIAS@VSAFilter@@QEBAJPEAUIAttributesRaw@@@Z` at `0x180013fb9`

## string_xrefs

- `0x180013f52`: `No AUTHENTICATION extensions, continuing`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall BaseCampHost::onSyncRequest(_BYTE *a1, struct IRequest *a2)
{
  PVOID *v4; // rax
  const _com_error *v6; // [rsp+20h] [rbp-28h] BYREF
  _BYTE v7[8]; // [rsp+28h] [rbp-20h] BYREF
  struct IAttributesRaw *v8; // [rsp+30h] [rbp-18h]

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Entering BaseCampHost stage");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids, "NPSSVC");
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1[96] )
  {
    if ( v4 != &WPP_GLOBAL_Control && *((_BYTE *)v4 + 25) >= 4u && (*((_BYTE *)v4 + 28) & 4) != 0 )
    {
      WppDbgPrint("No AUTHENTICATION extensions, continuing");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids, "NPSSVC");
    }
  }
  else
  {
    try
    {
      IASTL::IASRequest::IASRequest((IASTL::IASRequest *)v7, a2);
      VSAFilter::radiusFromIAS((VSAFilter *)(a1 + 80), v8, 0);
      BaseCampHostBase::ProcessExtensions((BaseCampHostBase *)a1, (struct IASTL::IASRequest *)v7);
      VSAFilter::radiusToIAS((VSAFilter *)(a1 + 80), v8);
      (*(void (__fastcall **)(struct IAttributesRaw *))(*(_QWORD *)v8 + 16LL))(v8);
    }
    catch ( const _com_error *v6 )
    {
      IASTraceExcept();
    }
    catch ( std::bad_alloc )
    {
      IASTraceExcept();
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180013ec0  mov     [rsp+arg_0], rbx
0x180013ec5  mov     [rsp+arg_10], rsi
0x180013eca  mov     [rsp+arg_8], rdx
0x180013ecf  push    rdi
0x180013ed0  sub     rsp, 40h
0x180013ed4  mov     rdi, rdx
0x180013ed7  mov     rbx, rcx
0x180013eda  lea     rsi, WPP_GLOBAL_Control
0x180013ee1  mov     rax, cs:WPP_GLOBAL_Control
0x180013ee8  cmp     rax, rsi
0x180013eeb  jz      short loc_180013F2F
0x180013eed  cmp     byte ptr [rax+19h], 4
0x180013ef1  jb      short loc_180013F2F
0x180013ef3  test    byte ptr [rax+1Ch], 4
0x180013ef7  jz      short loc_180013F2F
0x180013ef9  lea     rcx, aEnteringBaseca; "Entering BaseCampHost stage"
0x180013f00  call    WppDbgPrint
0x180013f05  mov     edx, 22h ; '"'
0x180013f0a  lea     r9, aNpssvc; "NPSSVC"
0x180013f11  lea     r8, WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids
0x180013f18  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f1f  mov     rcx, [rcx+10h]
0x180013f23  call    WPP_SF_s
0x180013f28  mov     rax, cs:WPP_GLOBAL_Control
0x180013f2f  cmp     byte ptr [rbx+60h], 0
0x180013f33  jz      short loc_180013F83
0x180013f35  cmp     rax, rsi
0x180013f38  jz      loc_180013FD6
0x180013f3e  cmp     byte ptr [rax+19h], 4
0x180013f42  jb      loc_180013FD6
0x180013f48  test    byte ptr [rax+1Ch], 4
0x180013f4c  jz      loc_180013FD6
0x180013f52  lea     rcx, aNoAuthenticati; "No AUTHENTICATION extensions, continuin"...
0x180013f59  call    WppDbgPrint
0x180013f5e  mov     edx, 23h ; '#'
0x180013f63  lea     r9, aNpssvc; "NPSSVC"
0x180013f6a  lea     r8, WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids
0x180013f71  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f78  mov     rcx, [rcx+10h]
0x180013f7c  call    WPP_SF_s
0x180013f81  jmp     short loc_180013FD6
0x180013f83  mov     rdx, rdi; struct IRequest *
0x180013f86  lea     rcx, [rsp+48h+var_20]; this
0x180013f8b  call    ??0IASRequest@IASTL@@QEAA@PEAUIRequest@@@Z; IASTL::IASRequest::IASRequest(IRequest *)
0x180013f90  nop
0x180013f91  xor     r8d, r8d
0x180013f94  mov     rdx, [rsp+48h+var_18]
0x180013f99  lea     rcx, [rbx+50h]
0x180013f9d  call    cs:__imp_?radiusFromIAS@VSAFilter@@QEBAJPEAUIAttributesRaw@@H@Z; VSAFilter::radiusFromIAS(IAttributesRaw *,int)
0x180013fa3  lea     rdx, [rsp+48h+var_20]; struct IASTL::IASRequest *
0x180013fa8  mov     rcx, rbx; this
0x180013fab  call    ?ProcessExtensions@BaseCampHostBase@@IEAAXAEAVIASRequest@IASTL@@@Z; BaseCampHostBase::ProcessExtensions(IASTL::IASRequest &)
0x180013fb0  mov     rdx, [rsp+48h+var_18]
0x180013fb5  lea     rcx, [rbx+50h]
0x180013fb9  call    cs:__imp_?radiusToIAS@VSAFilter@@QEBAJPEAUIAttributesRaw@@@Z; VSAFilter::radiusToIAS(IAttributesRaw *)
0x180013fbf  nop
0x180013fc0  mov     rcx, [rsp+48h+var_18]
0x180013fc5  mov     rax, [rcx]
0x180013fc8  mov     rax, [rax+10h]
0x180013fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fd1  nop
0x180013fd2  jmp     short loc_180013FD6
0x180013fd4  jmp     short $+2
0x180013fd6  mov     eax, 1
0x180013fdb  mov     rbx, [rsp+48h+arg_0]
0x180013fe0  mov     rsi, [rsp+48h+arg_10]
0x180013fe5  add     rsp, 40h
0x180013fe9  pop     rdi
0x180013fea  retn
```
