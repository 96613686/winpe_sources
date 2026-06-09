# _lambda_cb293c6ec7bc4deeec064c1f58322c0f_::operator()

- ea: `0x18002f20c`
- end: `0x18002f4e6`
- name: `_lambda_cb293c6ec7bc4deeec064c1f58322c0f_::operator()`
- size: `730`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002dd98`

## callees

- `0x18000270c`
- `0x180003740`
- `0x180011b9c`
- `0x180012004`
- `0x180012384`
- `0x18002e13c`
- `0x18002f20c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f2bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f2bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f2de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f2de`
- `deviceassociation!DafMemFree` at `0x18002f2a6`
- `deviceassociation!DafMemFree` at `0x18002f43b`
- `deviceassociation!DafMemFree` at `0x18002f2a6`
- `deviceassociation!DafMemFree` at `0x18002f43b`
- `deviceassociation!DafCreateAssociationContextFromOobBlob` at `0x18002f410`
- `deviceassociation!DafCreateAssociationContextFromOobBlob` at `0x18002f410`
- `deviceassociation!DafCloseAssociationContext` at `0x18002f2d0`
- `deviceassociation!DafCloseAssociationContext` at `0x18002f2d0`

## string_xrefs

- `0x18002f4d4`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
int *__fastcall lambda_cb293c6ec7bc4deeec064c1f58322c0f_::operator()(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD *v4; // rsi
  char v5; // di
  __int64 v6; // rcx
  __int64 v7; // r14
  DWORD LastError; // ebx
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // edx
  int v12; // r8d
  _BYTE *v13; // rcx
  _UNKNOWN **v14; // rax
  bool v15; // dl
  _QWORD *v16; // rcx
  __int64 v17; // r8
  __int64 v18; // rcx
  int *result; // rax
  unsigned int v20; // eax
  __int64 *v21; // [rsp+50h] [rbp-30h]
  int v22[2]; // [rsp+58h] [rbp-28h] BYREF
  char v23; // [rsp+60h] [rbp-20h]
  _QWORD v24[2]; // [rsp+68h] [rbp-18h] BYREF
  char v25; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v4 = *(_QWORD **)a1;
  v5 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, *((_QWORD *)WPP_GLOBAL_Control + 5));
  v6 = v4[8];
  v4[8] = 0;
  if ( v6 )
    DafMemFree(v6, a2, a3);
  v7 = v4[255];
  if ( v7 )
  {
    LastError = GetLastError();
    DafCloseAssociationContext(v7, v9, v10);
    SetLastError(LastError);
  }
  v4[255] = 0;
  memset_0(v4 + 19, 0, 0x760u);
  v13 = WPP_GLOBAL_Control;
  LOBYTE(v11) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  v14 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v12, *((_QWORD *)WPP_GLOBAL_Control + 5));
    v13 = WPP_GLOBAL_Control;
    v14 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  }
  v15 = v13 != (_BYTE *)&WPP_GLOBAL_Control && v13[25] >= 4u;
  if ( v15 || v14 != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)v13 + 2), v15, v14 != &WPP_RECORDER_INITIALIZED, *((_QWORD *)v13 + 5));
  v16 = *(_QWORD **)a1;
  v24[0] = *(_QWORD *)a1 + 2040LL;
  v24[1] = 0;
  v25 = 1;
  v21 = v16 + 8;
  *(_QWORD *)v22 = 0;
  v23 = 1;
  **(_DWORD **)(a1 + 8) = DafCreateAssociationContextFromOobBlob(&DAF_ProtocolId_BluetoothLE, 71, byte_1800463E0);
  if ( v23 )
  {
    v18 = *v21;
    *v21 = *(_QWORD *)v22;
    if ( v18 )
      DafMemFree(v18, v21, v17);
  }
  wil::details::out_param_ptr_t<DAF_ASSOCIATION_HANDLE__ * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DAF_ASSOCIATION_HANDLE__ *,long (*)(DAF_ASSOCIATION_HANDLE__ *),&long DafCloseAssociationContext(DAF_ASSOCIATION_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,DAF_ASSOCIATION_HANDLE__ *,DAF_ASSOCIATION_HANDLE__ *,0,std::nullptr_t>>>>::~out_param_ptr_t<DAF_ASSOCIATION_HANDLE__ * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DAF_ASSOCIATION_HANDLE__ *,long (*)(DAF_ASSOCIATION_HANDLE__ *),&long DafCloseAssociationContext(DAF_ASSOCIATION_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,DAF_ASSOCIATION_HANDLE__ *,DAF_ASSOCIATION_HANDLE__ *,0,std::nullptr_t>>>>(v24);
  result = *(int **)(a1 + 8);
  if ( *result < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      v5 = 0;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v5,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
    v20 = wil::verify_hresult<long>(**(unsigned int **)(a1 + 8));
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x22E,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v20,
      (int)v22);
  }
  return result;
}

```

## disassembly

```asm
0x18002f20c  mov     rax, rsp
0x18002f20f  mov     [rax+8], rbx
0x18002f213  mov     [rax+10h], rsi
0x18002f217  mov     [rax+18h], rdi
0x18002f21b  mov     [rax+20h], r13
0x18002f21f  push    rbp
0x18002f220  push    r14
0x18002f222  push    r15
0x18002f224  mov     rbp, rsp
0x18002f227  sub     rsp, 80h
0x18002f22e  mov     r15, rcx
0x18002f231  mov     rsi, [rcx]
0x18002f234  lea     r13, WPP_GLOBAL_Control
0x18002f23b  mov     dil, 1
0x18002f23e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f245  cmp     rcx, r13
0x18002f248  jz      short loc_18002F255
0x18002f24a  cmp     byte ptr [rcx+19h], 5
0x18002f24e  jb      short loc_18002F255
0x18002f250  mov     dl, dil
0x18002f253  jmp     short loc_18002F257
0x18002f255  xor     dl, dl
0x18002f257  lea     rbx, WPP_RECORDER_INITIALIZED
0x18002f25e  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x18002f265  setnz   r8b
0x18002f269  lea     r9, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002f270  test    dl, dl
0x18002f272  jnz     short loc_18002F279
0x18002f274  test    r8b, r8b
0x18002f277  jz      short loc_18002F298
0x18002f279  mov     [rsp+80h+var_38], rsi
0x18002f27e  mov     [rsp+80h+var_48], r9
0x18002f283  mov     word ptr [rsp+80h+var_50], 40h ; '@'
0x18002f28a  mov     r9, [rcx+28h]
0x18002f28e  mov     rcx, [rcx+10h]
0x18002f292  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002f297  nop
0x18002f298  mov     rcx, [rsi+40h]
0x18002f29c  and     qword ptr [rsi+40h], 0
0x18002f2a1  test    rcx, rcx
0x18002f2a4  jz      short loc_18002F2B3
0x18002f2a6  call    cs:__imp_DafMemFree
0x18002f2ad  nop     dword ptr [rax+rax+00h]
0x18002f2b2  nop
0x18002f2b3  mov     r14, [rsi+7F8h]
0x18002f2ba  test    r14, r14
0x18002f2bd  jz      short loc_18002F2F2
0x18002f2bf  call    cs:__imp_GetLastError
0x18002f2c6  nop     dword ptr [rax+rax+00h]
0x18002f2cb  mov     ebx, eax
0x18002f2cd  mov     rcx, r14
0x18002f2d0  call    cs:__imp_DafCloseAssociationContext
0x18002f2d7  nop     dword ptr [rax+rax+00h]
0x18002f2dc  mov     ecx, ebx; dwErrCode
0x18002f2de  call    cs:__imp_SetLastError
0x18002f2e5  nop     dword ptr [rax+rax+00h]
0x18002f2ea  nop
0x18002f2eb  lea     rbx, WPP_RECORDER_INITIALIZED
0x18002f2f2  and     qword ptr [rsi+7F8h], 0
0x18002f2fa  lea     rcx, [rsi+98h]; void *
0x18002f301  xor     edx, edx; Val
0x18002f303  mov     r8d, 760h; Size
0x18002f309  call    memset_0
0x18002f30e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f315  cmp     rcx, r13
0x18002f318  jz      short loc_18002F325
0x18002f31a  cmp     byte ptr [rcx+19h], 5
0x18002f31e  jb      short loc_18002F325
0x18002f320  mov     dl, dil
0x18002f323  jmp     short loc_18002F327
0x18002f325  xor     dl, dl
0x18002f327  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18002f32e  cmp     rax, rbx
0x18002f331  setnz   r8b
0x18002f335  test    dl, dl
0x18002f337  jnz     short loc_18002F33E
0x18002f339  test    r8b, r8b
0x18002f33c  jz      short loc_18002F373
0x18002f33e  mov     [rsp+80h+var_38], rsi
0x18002f343  lea     rsi, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002f34a  mov     [rsp+80h+var_48], rsi
0x18002f34f  mov     word ptr [rsp+80h+var_50], 41h ; 'A'
0x18002f356  mov     r9, [rcx+28h]
0x18002f35a  mov     rcx, [rcx+10h]
0x18002f35e  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002f363  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f36a  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18002f371  jmp     short loc_18002F37A
0x18002f373  lea     rsi, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002f37a  cmp     rcx, r13
0x18002f37d  jz      short loc_18002F38A
0x18002f37f  cmp     byte ptr [rcx+19h], 4
0x18002f383  jb      short loc_18002F38A
0x18002f385  mov     dl, dil
0x18002f388  jmp     short loc_18002F38C
0x18002f38a  xor     dl, dl
0x18002f38c  cmp     rax, rbx
0x18002f38f  setnz   r8b
0x18002f393  test    dl, dl
0x18002f395  jnz     short loc_18002F39C
0x18002f397  test    r8b, r8b
0x18002f39a  jz      short loc_18002F3B5
0x18002f39c  mov     [rsp+80h+var_48], rsi
0x18002f3a1  mov     word ptr [rsp+80h+var_50], 36h ; '6'
0x18002f3a8  mov     r9, [rcx+28h]
0x18002f3ac  mov     rcx, [rcx+10h]
0x18002f3b0  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002f3b5  mov     rcx, [r15]
0x18002f3b8  lea     rax, [rcx+7F8h]
0x18002f3bf  mov     [rbp+var_18], rax
0x18002f3c3  and     [rbp+var_10], 0
0x18002f3c8  mov     [rbp+var_8], dil
0x18002f3cc  lea     rax, [rcx+40h]
0x18002f3d0  mov     [rbp+var_30], rax
0x18002f3d4  and     qword ptr [rbp+var_28], 0
0x18002f3d9  mov     [rbp+var_20], dil
0x18002f3dd  and     [rsp+80h+var_48], 0
0x18002f3e3  and     [rsp+80h+var_50], 0
0x18002f3e9  lea     rax, [rbp+var_10]
0x18002f3ed  mov     [rsp+80h+var_58], rax
0x18002f3f2  lea     rax, [rbp+var_28]
0x18002f3f6  mov     qword ptr [rsp+80h+var_60], rax; int
0x18002f3fb  xor     r9d, r9d
0x18002f3fe  lea     r8, byte_1800463E0
0x18002f405  lea     edx, [r9+47h]
0x18002f409  lea     rcx, DAF_ProtocolId_BluetoothLE
0x18002f410  call    cs:__imp_DafCreateAssociationContextFromOobBlob
0x18002f417  nop     dword ptr [rax+rax+00h]
0x18002f41c  mov     rcx, [r15+8]
0x18002f420  mov     [rcx], eax
0x18002f422  cmp     [rbp+var_20], 0
0x18002f426  jz      short loc_18002F448
0x18002f428  mov     rdx, [rbp+var_30]
0x18002f42c  mov     rcx, [rdx]
0x18002f42f  mov     rax, qword ptr [rbp+var_28]
0x18002f433  mov     [rdx], rax
0x18002f436  test    rcx, rcx
0x18002f439  jz      short loc_18002F448
0x18002f43b  call    cs:__imp_DafMemFree
0x18002f442  nop     dword ptr [rax+rax+00h]
0x18002f447  nop
0x18002f448  lea     rcx, [rbp+var_18]
0x18002f44c  call    ??1?$out_param_ptr_t@PEAPEAUDAF_ASSOCIATION_HANDLE__@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUDAF_ASSOCIATION_HANDLE__@@P6AJPEAU1@@Z$1?DafCloseAssociationContext@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<DAF_ASSOCIATION_HANDLE__ * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DAF_ASSOCIATION_HANDLE__ *,long (*)(DAF_ASSOCIATION_HANDLE__ *),&DafCloseAssociationContext(DAF_ASSOCIATION_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,DAF_ASSOCIATION_HANDLE__ *,DAF_ASSOCIATION_HANDLE__ *,0,std::nullptr_t>>>>::~out_param_ptr_t<DAF_ASSOCIATION_HANDLE__ * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DAF_ASSOCIATION_HANDLE__ *,long (*)(DAF_ASSOCIATION_HANDLE__ *),&DafCloseAssociationContext(DAF_ASSOCIATION_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,DAF_ASSOCIATION_HANDLE__ *,DAF_ASSOCIATION_HANDLE__ *,0,std::nullptr_t>>>>(void)
0x18002f451  mov     rax, [r15+8]
0x18002f455  cmp     dword ptr [rax], 0
0x18002f458  jl      short loc_18002F47C
0x18002f45a  lea     r11, [rsp+80h+var_s0]
0x18002f462  mov     rbx, [r11+20h]
0x18002f466  mov     rsi, [r11+28h]
0x18002f46a  mov     rdi, [r11+30h]
0x18002f46e  mov     r13, [r11+38h]
0x18002f472  mov     rsp, r11
0x18002f475  pop     r15
0x18002f477  pop     r14
0x18002f479  pop     rbp
0x18002f47a  retn
0x18002f47c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f483  cmp     rcx, r13
0x18002f486  jz      short loc_18002F48E
0x18002f488  cmp     byte ptr [rcx+19h], 2
0x18002f48c  jnb     short loc_18002F491
0x18002f48e  xor     dil, dil
0x18002f491  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x18002f498  setnz   r8b
0x18002f49c  test    dil, dil
0x18002f49f  jnz     short loc_18002F4A6
0x18002f4a1  test    r8b, r8b
0x18002f4a4  jz      short loc_18002F4C2
0x18002f4a6  mov     [rsp+80h+var_48], rsi
0x18002f4ab  mov     word ptr [rsp+80h+var_50], 37h ; '7'
0x18002f4b2  mov     r9, [rcx+28h]
0x18002f4b6  mov     dl, dil
0x18002f4b9  mov     rcx, [rcx+10h]
0x18002f4bd  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002f4c2  mov     rcx, [r15+8]
0x18002f4c6  mov     ecx, [rcx]
0x18002f4c8  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002f4cd  mov     r9d, eax; char *
0x18002f4d0  mov     rcx, [rbp+18h]; this
0x18002f4d4  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002f4db  mov     edx, 22Eh; void *
0x18002f4e0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
