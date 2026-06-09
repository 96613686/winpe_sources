# EAPSession::~EAPSession(void)

- ea: `0x180018620`
- end: `0x180018792`
- name: `??1EAPSession@@QEAA@XZ`
- size: `370`
- prototype: `void __fastcall(EAPSession *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016b7c`

## callees

- `0x18000acf4`
- `0x18000b2dc`
- `0x18000c500`
- `0x180018620`
- `0x180018aac`
- `0x180018b10`
- `0x180018b48`
- `0x180018b88`
- `0x1800254a0`
- `0x18002e010`

## import_xrefs

- `msvcrt!free` at `0x180018651`
- `msvcrt!free` at `0x18001865e`
- `msvcrt!free` at `0x18001875e`
- `msvcrt!free` at `0x180018651`
- `msvcrt!free` at `0x18001865e`
- `msvcrt!free` at `0x18001875e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018639`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018639`

## pseudocode

```c
void __fastcall EAPSession::~EAPSession(EAPSession *this)
{
  void *v2; // rcx
  __int64 v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  struct _EAP_ERROR *v6; // [rsp+40h] [rbp+8h] BYREF

  v2 = (void *)*((_QWORD *)this + 24);
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *((_QWORD *)this + 24) = 0;
  }
  free(*((void **)this + 25));
  free(*((void **)this + 22));
  FreeEAPAttributes((struct _EAP_ATTRIBUTES *)this + 19);
  FreeEAPAttributes((struct _EAP_ATTRIBUTES *)this + 20);
  FreeEAPMethods((EAPSession *)((char *)this + 280));
  FreeEAPMethodInfo(*((struct _EAP_METHOD_INFO **)this + 37));
  v6 = 0;
  v3 = *((_QWORD *)this + 44);
  if ( v3 )
  {
    if ( (*(int (__fastcall **)(__int64, _QWORD, struct _EAP_ERROR **))(*(_QWORD *)v3 + 104LL))(
           v3,
           *((unsigned int *)this + 87),
           &v6) < 0 )
    {
      FreeEAPError(v6);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("EapHostAuthenticatorEndSession failed with 0x%x");
        WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_69033002015f3c629418a4473ed337be_Traceguids);
      }
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 44) + 16LL))(*((_QWORD *)this + 44));
    *((_QWORD *)this + 44) = 0;
  }
  IASTL::IASAttributeVector::~IASAttributeVector((EAPSession *)((char *)this + 248));
  IASTL::IASAttributeVector::~IASAttributeVector((EAPSession *)((char *)this + 224));
  free(*((void **)this + 26));
  v4 = (void *)*((_QWORD *)this + 21);
  if ( v4 )
    IASAttributeRelease(v4);
  v5 = (void *)*((_QWORD *)this + 20);
  if ( v5 )
    IASAttributeRelease(v5);
}

```

## disassembly

```asm
0x180018620  mov     [rsp+arg_8], rbx
0x180018625  push    rdi
0x180018626  sub     rsp, 30h
0x18001862a  mov     rbx, rcx
0x18001862d  mov     rcx, [rcx+0C0h]; pv
0x180018634  test    rcx, rcx
0x180018637  jz      short loc_18001864A
0x180018639  call    cs:__imp_CoTaskMemFree
0x18001863f  mov     qword ptr [rbx+0C0h], 0
0x18001864a  mov     rcx, [rbx+0C8h]; Block
0x180018651  call    cs:__imp_free
0x180018657  mov     rcx, [rbx+0B0h]; Block
0x18001865e  call    cs:__imp_free
0x180018664  lea     rcx, [rbx+130h]; struct _EAP_ATTRIBUTES *
0x18001866b  call    ?FreeEAPAttributes@@YAXAEAU_EAP_ATTRIBUTES@@@Z; FreeEAPAttributes(_EAP_ATTRIBUTES &)
0x180018670  lea     rcx, [rbx+140h]; struct _EAP_ATTRIBUTES *
0x180018677  call    ?FreeEAPAttributes@@YAXAEAU_EAP_ATTRIBUTES@@@Z; FreeEAPAttributes(_EAP_ATTRIBUTES &)
0x18001867c  lea     rcx, [rbx+118h]; struct _EAP_HOST_AUTHENTICATOR_METHOD_DATA_ARRAY *
0x180018683  call    ?FreeEAPMethods@@YAXAEAU_EAP_HOST_AUTHENTICATOR_METHOD_DATA_ARRAY@@@Z; FreeEAPMethods(_EAP_HOST_AUTHENTICATOR_METHOD_DATA_ARRAY &)
0x180018688  mov     rcx, [rbx+128h]; struct _EAP_METHOD_INFO *
0x18001868f  call    ?FreeEAPMethodInfo@@YAXPEAU_EAP_METHOD_INFO@@@Z; FreeEAPMethodInfo(_EAP_METHOD_INFO *)
0x180018694  mov     [rsp+38h+arg_0], 0
0x18001869d  mov     rcx, [rbx+160h]
0x1800186a4  test    rcx, rcx
0x1800186a7  jz      loc_18001873F
0x1800186ad  mov     rax, [rcx]
0x1800186b0  lea     r8, [rsp+38h+arg_0]
0x1800186b5  mov     edx, [rbx+15Ch]
0x1800186bb  mov     rax, [rax+68h]
0x1800186bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186c4  mov     edi, eax
0x1800186c6  test    eax, eax
0x1800186c8  jns     short loc_180018721
0x1800186ca  mov     rcx, [rsp+38h+arg_0]; struct _EAP_ERROR *
0x1800186cf  call    ?FreeEAPError@@YAXPEAU_EAP_ERROR@@@Z; FreeEAPError(_EAP_ERROR *)
0x1800186d4  lea     rax, WPP_GLOBAL_Control
0x1800186db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800186e2  cmp     rcx, rax
0x1800186e5  jz      short loc_180018721
0x1800186e7  cmp     byte ptr [rcx+19h], 2
0x1800186eb  jb      short loc_180018721
0x1800186ed  test    byte ptr [rcx+1Ch], 4
0x1800186f1  jz      short loc_180018721
0x1800186f3  mov     edx, edi
0x1800186f5  lea     rcx, aEaphostauthent_0; "EapHostAuthenticatorEndSession failed w"...
0x1800186fc  call    WppDbgPrint
0x180018701  mov     edx, 0Fh
0x180018706  mov     [rsp+38h+var_18], edi
0x18001870a  lea     r8, WPP_69033002015f3c629418a4473ed337be_Traceguids
0x180018711  mov     rcx, cs:WPP_GLOBAL_Control
0x180018718  mov     rcx, [rcx+10h]
0x18001871c  call    WPP_SF_sd
0x180018721  mov     rcx, [rbx+160h]
0x180018728  mov     rax, [rcx]
0x18001872b  mov     rax, [rax+10h]
0x18001872f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018734  mov     qword ptr [rbx+160h], 0
0x18001873f  lea     rcx, [rbx+0F8h]; this
0x180018746  call    ??1IASAttributeVector@IASTL@@QEAA@XZ; IASTL::IASAttributeVector::~IASAttributeVector(void)
0x18001874b  lea     rcx, [rbx+0E0h]; this
0x180018752  call    ??1IASAttributeVector@IASTL@@QEAA@XZ; IASTL::IASAttributeVector::~IASAttributeVector(void)
0x180018757  mov     rcx, [rbx+0D0h]; Block
0x18001875e  call    cs:__imp_free
0x180018764  mov     rcx, [rbx+0A8h]; pv
0x18001876b  test    rcx, rcx
0x18001876e  jz      short loc_180018775
0x180018770  call    IASAttributeRelease
0x180018775  mov     rcx, [rbx+0A0h]; pv
0x18001877c  test    rcx, rcx
0x18001877f  jz      short loc_180018787
0x180018781  call    IASAttributeRelease
0x180018786  nop
0x180018787  mov     rbx, [rsp+38h+arg_8]
0x18001878c  add     rsp, 30h
0x180018790  pop     rdi
0x180018791  retn
```
