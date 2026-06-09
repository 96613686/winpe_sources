# HcsGetLayerVhdMountPath

- ea: `0x180014e80`
- end: `0x180015047`
- name: `HcsGetLayerVhdMountPath`
- size: `455`
- prototype: `HRESULT __stdcall(HANDLE vhdHandle, PWSTR *mountPath)`
- caller_count: `0`
- callee_count: `14`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002690`
- `0x1800032b8`
- `0x1800084b4`
- `0x1800084c0`
- `0x180008ce8`
- `0x180008fac`
- `0x18000a964`
- `0x18000ad80`
- `0x18000fa98`
- `0x18000ffd4`
- `0x1800127bc`
- `0x180014e80`
- `0x180015be8`
- `0x1800283b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014f62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014f62`

## string_xrefs

- `0x180015034`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180014ec4`: `ComputeStorage_HcsGetLayerVhdMountPath`
- `0x180015023`: `onecore\vm\compute\dll\storage\src\layer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall HcsGetLayerVhdMountPath(HANDLE vhdHandle, PWSTR *mountPath)
{
  const char *v4; // r9
  void **v5; // rbx
  char v6; // al
  __int64 v7; // rax
  __int64 v8; // rcx
  char *v9; // rax
  rsize_t v10; // r14
  WCHAR *v11; // rax
  WCHAR *v12; // rdi
  WCHAR *v13; // rsi
  const char *v14; // r9
  HRESULT result; // eax
  const char *v16; // r9
  int v17; // [rsp+20h] [rbp-1B8h]
  void *Source[5]; // [rsp+28h] [rbp-1B0h] BYREF
  _QWORD v19[42]; // [rsp+50h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  memset_0(v19, 0, sizeof(v19));
  wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v19,
    (__int64)"ComputeStorage_HcsGetLayerVhdMountPath");
  v19[0] = &ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsGetLayerVhdMountPath::`vftable';
  ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsGetLayerVhdMountPath::StartActivity((ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsGetLayerVhdMountPath *)v19);
  try
  {
    if ( !mountPath )
    {
      v16 = (const char *)(unsigned int)wil::verify_hresult<long>(0x80070057);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1D8,
        (unsigned int)"onecore\\vm\\compute\\dll\\storage\\src\\layer.cpp",
        v16,
        v17);
    }
    GetVhdVolumePath((WCHAR *)Source, vhdHandle);
    if ( Source[3] <= (void *)7 )
    {
      v5 = Source;
    }
    else
    {
      v5 = (void **)Source[0];
      if ( !Source[0] )
      {
        v6 = 1;
LABEL_8:
        if ( v6 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xF89,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v4);
        v7 = -1;
        if ( v5 )
        {
          v8 = 0x7FFFFFFF;
          v9 = (char *)v5;
          do
          {
            if ( !*(_WORD *)v9 )
              break;
            v9 += 2;
            --v8;
          }
          while ( v8 );
          v7 = (v9 - (char *)v5) >> 1;
        }
        v10 = 2 * v7;
        v11 = (WCHAR *)CoTaskMemAlloc(2 * v7 + 2);
        v12 = v11;
        if ( v11 )
        {
          v13 = &v11[v10 / 2];
          if ( v5 )
          {
            memcpy_s(v11, v10 + 2, v5, v10);
            *v13 = 0;
          }
          else
          {
            *v11 = 0;
          }
          *v13 = 0;
        }
        *mountPath = v12;
        wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v19);
        std::wstring::~wstring((char **)Source);
        v19[0] = &ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsGetLayerVhdMountPath::`vftable';
        wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v19);
        wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v19);
        return 0;
      }
    }
    v6 = 0;
    goto LABEL_8;
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Return_CaughtException(
             retaddr,
             (void *)0x1E1,
             (unsigned int)"onecore\\vm\\compute\\dll\\storage\\src\\layer.cpp",
             v14);
  }
  return result;
}

```

## disassembly

```asm
0x180014e80  mov     [rsp+arg_10], rbx
0x180014e85  mov     [rsp+arg_18], rsi
0x180014e8a  push    rdi
0x180014e8b  push    r12
0x180014e8d  push    r13
0x180014e8f  push    r14
0x180014e91  push    r15
0x180014e93  sub     rsp, 1B0h
0x180014e9a  mov     rax, cs:__security_cookie
0x180014ea1  xor     rax, rsp
0x180014ea4  mov     [rsp+1D8h+var_38], rax
0x180014eac  mov     r12, rdx
0x180014eaf  mov     rbx, rcx
0x180014eb2  xor     edx, edx; Val
0x180014eb4  mov     r8d, 150h; Size
0x180014eba  lea     rcx, [rsp+1D8h+var_188]; void *
0x180014ebf  call    memset_0
0x180014ec4  lea     rdx, aComputestorage_9; "ComputeStorage_HcsGetLayerVhdMountPath"
0x180014ecb  lea     rcx, [rsp+1D8h+var_188]
0x180014ed0  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180014ed5  lea     rax, ??_7ComputeStorage_HcsGetLayerVhdMountPath@TraceProvider@Diagnostics@ComputeStorage@@6B@; const ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsGetLayerVhdMountPath::`vftable'
0x180014edc  mov     [rsp+1D8h+var_188], rax
0x180014ee1  lea     rcx, [rsp+1D8h+var_188]; this
0x180014ee6  call    ?StartActivity@ComputeStorage_HcsGetLayerVhdMountPath@TraceProvider@Diagnostics@ComputeStorage@@QEAAXXZ; ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsGetLayerVhdMountPath::StartActivity(void)
0x180014eeb  nop
0x180014eec  xor     r13d, r13d
0x180014eef  test    r12, r12
0x180014ef2  jz      loc_18001500E
0x180014ef8  mov     rdx, rbx; VirtualDiskHandle
0x180014efb  lea     rcx, [rsp+1D8h+Source]; Src
0x180014f00  call    ?GetVhdVolumePath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; GetVhdVolumePath(void *)
0x180014f05  cmp     [rsp+1D8h+var_198], 7
0x180014f0b  jbe     short loc_180014F1B
0x180014f0d  mov     rbx, [rsp+1D8h+Source]
0x180014f12  test    rbx, rbx
0x180014f15  jnz     short loc_180014F20
0x180014f17  mov     al, 1
0x180014f19  jmp     short loc_180014F23
0x180014f1b  lea     rbx, [rsp+1D8h+Source]
0x180014f20  mov     al, r13b
0x180014f23  mov     rcx, [rsp+1D8h]; this
0x180014f2b  test    al, al
0x180014f2d  jnz     loc_180015034
0x180014f33  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014f37  test    rbx, rbx
0x180014f3a  jz      short loc_180014F5A
0x180014f3c  mov     ecx, 7FFFFFFFh
0x180014f41  mov     rax, rbx
0x180014f44  cmp     [rax], r13w
0x180014f48  jz      short loc_180014F54
0x180014f4a  add     rax, 2
0x180014f4e  sub     rcx, 1
0x180014f52  jnz     short loc_180014F44
0x180014f54  sub     rax, rbx
0x180014f57  sar     rax, 1
0x180014f5a  lea     r14, [rax+rax]
0x180014f5e  lea     rcx, [r14+2]; cb
0x180014f62  call    cs:__imp_CoTaskMemAlloc
0x180014f69  nop     dword ptr [rax+rax+00h]
0x180014f6e  mov     rdi, rax
0x180014f71  test    rax, rax
0x180014f74  jz      short loc_180014F9F
0x180014f76  lea     rsi, [r14+rax]
0x180014f7a  test    rbx, rbx
0x180014f7d  jz      short loc_180014F97
0x180014f7f  mov     r9, r14; SourceSize
0x180014f82  mov     r8, rbx; Source
0x180014f85  lea     rdx, [r14+2]; DestinationSize
0x180014f89  mov     rcx, rax; Destination
0x180014f8c  call    memcpy_s
0x180014f91  mov     [rsi], r13w
0x180014f95  jmp     short loc_180014F9B
0x180014f97  mov     [rax], r13w
0x180014f9b  mov     [rsi], r13w
0x180014f9f  mov     [r12], rdi
0x180014fa3  lea     rcx, [rsp+1D8h+var_188]
0x180014fa8  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180014fad  lea     rcx, [rsp+1D8h+Source]
0x180014fb2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014fb7  nop
0x180014fb8  lea     rax, ??_7ComputeStorage_HcsGetLayerVhdMountPath@TraceProvider@Diagnostics@ComputeStorage@@6B@; const ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsGetLayerVhdMountPath::`vftable'
0x180014fbf  mov     [rsp+1D8h+var_188], rax
0x180014fc4  lea     rcx, [rsp+1D8h+var_188]
0x180014fc9  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180014fce  lea     rcx, [rsp+1D8h+var_188]
0x180014fd3  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180014fd8  xor     eax, eax
0x180014fda  jmp     short loc_180014FE0
0x180014fdc  mov     eax, [rsp+1D8h+var_1B8]
0x180014fe0  mov     rcx, [rsp+1D8h+var_38]
0x180014fe8  xor     rcx, rsp; StackCookie
0x180014feb  call    __security_check_cookie
0x180014ff0  lea     r11, [rsp+1D8h+var_28]
0x180014ff8  mov     rbx, [r11+40h]
0x180014ffc  mov     rsi, [r11+48h]
0x180015000  mov     rsp, r11
0x180015003  pop     r15
0x180015005  pop     r14
0x180015007  pop     r13
0x180015009  pop     r12
0x18001500b  pop     rdi
0x18001500c  retn
0x18001500e  mov     ecx, 80070057h
0x180015013  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180015018  mov     r9d, eax; char *
0x18001501b  mov     rcx, [rsp+1D8h]; this
0x180015023  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\dll\\storage\\src"...
0x18001502a  mov     edx, 1D8h; void *
0x18001502f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015034  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001503b  mov     edx, 0F89h; void *
0x180015040  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
