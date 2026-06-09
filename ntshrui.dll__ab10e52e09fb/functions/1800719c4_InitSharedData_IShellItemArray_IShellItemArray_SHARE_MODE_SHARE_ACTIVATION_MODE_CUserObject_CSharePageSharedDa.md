# InitSharedData(IShellItemArray *,IShellItemArray *,SHARE_MODE,SHARE_ACTIVATION_MODE,CUserObject *,CSharePageSharedData *)

- ea: `0x1800719c4`
- end: `0x180071ce2`
- name: `?InitSharedData@@YAJPEAUIShellItemArray@@0W4SHARE_MODE@@W4SHARE_ACTIVATION_MODE@@PEAVCUserObject@@PEAVCSharePageSharedData@@@Z`
- size: `798`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180071cf0`
- `0x180071e2c`

## callees

- `0x18000a430`
- `0x1800259bc`
- `0x18002ad00`
- `0x180053fd4`
- `0x180067e90`
- `0x18007029c`
- `0x180070344`
- `0x180070588`
- `0x1800719c4`
- `0x180078010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180071ad4`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180071ad4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180071c0d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180071c0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071b5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071b5a`
- `SHCORE!IsOS` at `0x180071bde`
- `SHCORE!IsOS` at `0x180071bde`

## pseudocode

```c
__int64 __fastcall InitSharedData(__int64 a1, __int64 a2, unsigned int a3, int a4, CUserObject *a5, __int64 a6)
{
  __int64 v6; // rsi
  int ShareEngineForMode; // edi
  __int64 v11; // rcx
  CUserObjectList **v12; // r15
  PSID v13; // r14
  __int64 i; // rbx
  _QWORD *v15; // rax
  CUserObject *v16; // rbx
  unsigned int v17; // edx
  __int64 v18; // rcx
  HRESULT v19; // eax
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  struct ISharePermissionList *v25; // [rsp+80h] [rbp+40h] BYREF
  PSID pSid2; // [rsp+88h] [rbp+48h] BYREF
  int v27; // [rsp+90h] [rbp+50h] BYREF
  int v28; // [rsp+98h] [rbp+58h] BYREF

  v6 = a6;
  *(_DWORD *)a6 = a3;
  *(_QWORD *)(v6 + 16) = a1;
  *(_DWORD *)(v6 + 8) = a4;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  *(_QWORD *)(v6 + 24) = a2;
  if ( a2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  a6 = 0;
  ShareEngineForMode = GetShareEngineForMode(a3, 0, a1, 0, a2, 0, &a6, 0);
  if ( ShareEngineForMode >= 0 )
  {
    v11 = a6;
    *(_QWORD *)(v6 + 56) = a6;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
    v25 = 0;
    ShareEngineForMode = (*(__int64 (__fastcall **)(__int64, struct ISharePermissionList **))(*(_QWORD *)a6 + 88LL))(
                           a6,
                           &v25);
    if ( ShareEngineForMode >= 0 )
    {
      v12 = (CUserObjectList **)(v6 + 40);
      ShareEngineForMode = CUserObjectList::CreateInstance(v25, (struct CUserObjectList **)(v6 + 40));
      (*(void (__fastcall **)(struct ISharePermissionList *))(*(_QWORD *)v25 + 16LL))(v25);
      if ( ShareEngineForMode >= 0 )
      {
        pSid2 = 0;
        ShareEngineForMode = GetCurrentUserSid(&pSid2);
        if ( ShareEngineForMode >= 0 )
        {
          v13 = pSid2;
          for ( i = *(_QWORD *)*v12; i; i = *(_QWORD *)(i + 56) )
          {
            if ( EqualSid(*(PSID *)i, v13) )
              goto LABEL_15;
          }
          v15 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
          pSid2 = v15;
          v16 = (CUserObject *)v15;
          if ( v15 )
          {
            v15[1] = 0;
            v15[2] = 0;
            v15[3] = 0;
            v15[4] = 0;
            v15[5] = 8;
            *((_DWORD *)v15 + 13) = 1;
            v15[7] = 0;
            *v15 = v13;
            *((_DWORD *)v15 + 12) = 2;
            v13 = 0;
            ShareEngineForMode = CUserObjectList::AddUser(*v12, (struct CUserObject *)v15);
            if ( ShareEngineForMode < 0 )
              CUserObject::`scalar deleting destructor'(v16, v17);
          }
          else
          {
            ShareEngineForMode = -2147024882;
          }
LABEL_15:
          CoTaskMemFree(v13);
          if ( ShareEngineForMode >= 0 )
          {
            if ( !a5
              || (pSid2 = 0,
                  ShareEngineForMode = CUserObject::Clone(a5, (struct CUserObject **)&pSid2),
                  ShareEngineForMode >= 0)
              && (ShareEngineForMode = CUserObjectList::AddUser(*v12, (struct CUserObject *)pSid2),
                  ShareEngineForMode >= 0) )
            {
              v18 = a6;
              v27 = 0;
              *(_DWORD *)(v6 + 92) = 2;
              ShareEngineForMode = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 144LL))(v18, &v27);
              if ( ShareEngineForMode >= 0 && v27 )
              {
                *(_DWORD *)(v6 + 92) = 1;
              }
              else if ( !IsOS(0x1Cu) )
              {
                pSid2 = 0;
                v19 = CoCreateInstance(
                        &GUID_1fda955b_61ff_11da_978c_0008744faab7,
                        0,
                        1u,
                        &GUID_1fda955c_61ff_11da_978c_0008744faab7,
                        &pSid2);
                if ( v19 < 0 )
                {
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      11,
                      WPP_8699e7370d6639d67dcf32da8b975182_Traceguids,
                      (unsigned int)v19);
                  }
                }
                else
                {
                  v28 = 0;
                  v20 = (*(__int64 (__fastcall **)(PSID, __int64, __int64, int *, _QWORD))(*(_QWORD *)pSid2 + 48LL))(
                          pSid2,
                          2,
                          3,
                          &v28,
                          0);
                  v23 = (unsigned int)v20;
                  if ( v20 < 0 )
                  {
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        10,
                        WPP_8699e7370d6639d67dcf32da8b975182_Traceguids,
                        (unsigned int)v20);
                    }
                  }
                  else if ( v28 != 1 )
                  {
                    *(_DWORD *)(v6 + 92) = 1;
                  }
                  (*(void (__fastcall **)(PSID, __int64, __int64, __int64))(*(_QWORD *)pSid2 + 16LL))(
                    pSid2,
                    v21,
                    v22,
                    v23);
                }
              }
            }
          }
        }
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 16LL))(a6);
  }
  return (unsigned int)ShareEngineForMode;
}

```

## disassembly

```asm
0x1800719c4  push    rbp
0x1800719c6  push    rbx
0x1800719c7  push    rsi
0x1800719c8  push    rdi
0x1800719c9  push    r12
0x1800719cb  push    r14
0x1800719cd  push    r15
0x1800719cf  mov     rbp, rsp
0x1800719d2  sub     rsp, 40h
0x1800719d6  mov     rsi, [rbp+arg_28]
0x1800719da  mov     r14d, r8d
0x1800719dd  mov     rbx, rdx
0x1800719e0  mov     rdi, rcx
0x1800719e3  mov     [rsi], r8d
0x1800719e6  mov     [rsi+10h], rcx
0x1800719ea  mov     [rsi+8], r9d
0x1800719ee  mov     rax, [rcx]
0x1800719f1  mov     rax, [rax+8]
0x1800719f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800719fa  xor     r12d, r12d
0x1800719fd  mov     [rsi+18h], rbx
0x180071a01  test    rbx, rbx
0x180071a04  jz      short loc_180071A15
0x180071a06  mov     rax, [rbx]
0x180071a09  mov     rcx, rbx
0x180071a0c  mov     rax, [rax+8]
0x180071a10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071a15  mov     [rsp+40h+var_8], r12
0x180071a1a  lea     rax, [rbp+arg_28]
0x180071a1e  mov     [rsp+40h+var_10], rax
0x180071a23  xor     r9d, r9d
0x180071a26  mov     [rsp+40h+var_18], r12
0x180071a2b  mov     r8, rdi
0x180071a2e  xor     edx, edx
0x180071a30  mov     [rsp+40h+ppv], rbx
0x180071a35  mov     ecx, r14d
0x180071a38  mov     [rbp+arg_28], r12
0x180071a3c  call    ?GetShareEngineForMode@@YAJW4SHARE_MODE@@HPEAUIShellItemArray@@PEAUIShareEngine@@1PEAUIMultiObjectElevationFactory@@PEAPEAU3@PEAUIShareProgressSink@@@Z; GetShareEngineForMode(SHARE_MODE,int,IShellItemArray *,IShareEngine *,IShellItemArray *,IMultiObjectElevationFactory *,IShareEngine * *,IShareProgressSink *)
0x180071a41  mov     edi, eax
0x180071a43  test    eax, eax
0x180071a45  js      loc_180071CD1
0x180071a4b  mov     rcx, [rbp+arg_28]
0x180071a4f  mov     [rsi+38h], rcx
0x180071a53  mov     rax, [rcx]
0x180071a56  mov     rax, [rax+8]
0x180071a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071a5f  mov     rcx, [rbp+arg_28]
0x180071a63  lea     rdx, [rbp+arg_0]
0x180071a67  mov     [rbp+arg_0], r12
0x180071a6b  mov     rax, [rcx]
0x180071a6e  mov     rax, [rax+58h]
0x180071a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071a77  mov     edi, eax
0x180071a79  test    eax, eax
0x180071a7b  js      loc_180071CC1
0x180071a81  mov     rcx, [rbp+arg_0]; struct ISharePermissionList *
0x180071a85  lea     r15, [rsi+28h]
0x180071a89  mov     rdx, r15; struct CUserObjectList **
0x180071a8c  call    ?CreateInstance@CUserObjectList@@SAJPEAUISharePermissionList@@PEAPEAV1@@Z; CUserObjectList::CreateInstance(ISharePermissionList *,CUserObjectList * *)
0x180071a91  mov     rcx, [rbp+arg_0]
0x180071a95  mov     edi, eax
0x180071a97  mov     rax, [rcx]
0x180071a9a  mov     rax, [rax+10h]
0x180071a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071aa3  test    edi, edi
0x180071aa5  js      loc_180071CC1
0x180071aab  lea     rcx, [rbp+pSid2]; void **
0x180071aaf  mov     [rbp+pSid2], r12
0x180071ab3  call    ?GetCurrentUserSid@@YAJPEAPEAX@Z; GetCurrentUserSid(void * *)
0x180071ab8  mov     edi, eax
0x180071aba  test    eax, eax
0x180071abc  js      loc_180071CC1
0x180071ac2  mov     rax, [r15]
0x180071ac5  mov     r14, [rbp+pSid2]
0x180071ac9  mov     rbx, [rax]
0x180071acc  jmp     short loc_180071AE2
0x180071ace  mov     rcx, [rbx]; pSid1
0x180071ad1  mov     rdx, r14; pSid2
0x180071ad4  call    cs:__imp_EqualSid
0x180071ada  test    eax, eax
0x180071adc  jnz     short loc_180071B57
0x180071ade  mov     rbx, [rbx+38h]
0x180071ae2  test    rbx, rbx
0x180071ae5  jnz     short loc_180071ACE
0x180071ae7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180071aee  lea     ecx, [rbx+40h]; unsigned __int64
0x180071af1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180071af6  mov     [rbp+pSid2], rax
0x180071afa  mov     rbx, rax
0x180071afd  test    rax, rax
0x180071b00  jz      short loc_180071B52
0x180071b02  mov     [rax+8], r12
0x180071b06  mov     [rax+10h], r12
0x180071b0a  mov     [rax+18h], r12
0x180071b0e  mov     [rax+20h], r12
0x180071b12  mov     qword ptr [rax+28h], 8
0x180071b1a  mov     dword ptr [rax+34h], 1
0x180071b21  mov     [rax+38h], r12
0x180071b25  mov     [rax], r14
0x180071b28  mov     dword ptr [rax+30h], 2
0x180071b2f  test    rax, rax
0x180071b32  jz      short loc_180071B52
0x180071b34  mov     rcx, [r15]; this
0x180071b37  mov     rdx, rax; struct CUserObject *
0x180071b3a  mov     r14, r12
0x180071b3d  call    ?AddUser@CUserObjectList@@QEAAJPEAVCUserObject@@@Z; CUserObjectList::AddUser(CUserObject *)
0x180071b42  mov     edi, eax
0x180071b44  test    eax, eax
0x180071b46  jns     short loc_180071B57
0x180071b48  mov     rcx, rbx; this
0x180071b4b  call    ??_GCUserObject@@QEAAPEAXI@Z; CUserObject::`scalar deleting destructor'(uint)
0x180071b50  jmp     short loc_180071B57
0x180071b52  mov     edi, 8007000Eh
0x180071b57  mov     rcx, r14; pv
0x180071b5a  call    cs:__imp_CoTaskMemFree
0x180071b60  test    edi, edi
0x180071b62  js      loc_180071CC1
0x180071b68  mov     rcx, [rbp+arg_20]; this
0x180071b6c  test    rcx, rcx
0x180071b6f  jz      short loc_180071B9E
0x180071b71  lea     rdx, [rbp+pSid2]; struct CUserObject **
0x180071b75  mov     [rbp+pSid2], r12
0x180071b79  call    ?Clone@CUserObject@@QEAAJPEAPEAV1@@Z; CUserObject::Clone(CUserObject * *)
0x180071b7e  mov     edi, eax
0x180071b80  test    eax, eax
0x180071b82  js      loc_180071CC1
0x180071b88  mov     rdx, [rbp+pSid2]; struct CUserObject *
0x180071b8c  mov     rcx, [r15]; this
0x180071b8f  call    ?AddUser@CUserObjectList@@QEAAJPEAVCUserObject@@@Z; CUserObjectList::AddUser(CUserObject *)
0x180071b94  mov     edi, eax
0x180071b96  test    eax, eax
0x180071b98  js      loc_180071CC1
0x180071b9e  mov     rcx, [rbp+arg_28]
0x180071ba2  lea     rdx, [rbp+arg_10]
0x180071ba6  mov     [rbp+arg_10], r12d
0x180071baa  mov     ebx, 2
0x180071baf  mov     [rsi+5Ch], ebx
0x180071bb2  mov     rax, [rcx]
0x180071bb5  mov     rax, [rax+90h]
0x180071bbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071bc1  mov     edi, eax
0x180071bc3  test    eax, eax
0x180071bc5  js      short loc_180071BD9
0x180071bc7  cmp     [rbp+arg_10], r12d
0x180071bcb  jz      short loc_180071BD9
0x180071bcd  mov     dword ptr [rsi+5Ch], 1
0x180071bd4  jmp     loc_180071CC1
0x180071bd9  mov     ecx, 1Ch; dwOS
0x180071bde  call    cs:__imp_IsOS
0x180071be4  test    eax, eax
0x180071be6  jnz     loc_180071CC1
0x180071bec  xor     edx, edx; pUnkOuter
0x180071bee  mov     [rbp+pSid2], r12
0x180071bf2  lea     rax, [rbp+pSid2]
0x180071bf6  lea     r9, _GUID_1fda955c_61ff_11da_978c_0008744faab7; riid
0x180071bfd  mov     [rsp+40h+ppv], rax; ppv
0x180071c02  lea     rcx, _GUID_1fda955b_61ff_11da_978c_0008744faab7; rclsid
0x180071c09  lea     r8d, [rdx+1]; dwClsContext
0x180071c0d  call    cs:__imp_CoCreateInstance
0x180071c13  mov     r9d, eax
0x180071c16  test    eax, eax
0x180071c18  js      short loc_180071C94
0x180071c1a  mov     rcx, [rbp+pSid2]
0x180071c1e  lea     r9, [rbp+arg_18]
0x180071c22  mov     [rbp+arg_18], r12d
0x180071c26  mov     r8d, 3
0x180071c2c  mov     edx, ebx
0x180071c2e  mov     [rsp+40h+ppv], r12
0x180071c33  mov     rax, [rcx]
0x180071c36  mov     rax, [rax+30h]
0x180071c3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071c3f  mov     r9d, eax
0x180071c42  test    eax, eax
0x180071c44  js      short loc_180071C55
0x180071c46  cmp     [rbp+arg_18], 1
0x180071c4a  jz      short loc_180071C82
0x180071c4c  mov     dword ptr [rsi+5Ch], 1
0x180071c53  jmp     short loc_180071C82
0x180071c55  mov     rcx, cs:WPP_GLOBAL_Control
0x180071c5c  lea     rax, WPP_GLOBAL_Control
0x180071c63  cmp     rcx, rax
0x180071c66  jz      short loc_180071C82
0x180071c68  test    [rcx+1Ch], bl
0x180071c6b  jz      short loc_180071C82
0x180071c6d  mov     rcx, [rcx+10h]
0x180071c71  lea     r8, WPP_8699e7370d6639d67dcf32da8b975182_Traceguids
0x180071c78  mov     edx, 0Ah
0x180071c7d  call    WPP_SF_d
0x180071c82  mov     rcx, [rbp+pSid2]
0x180071c86  mov     rax, [rcx]
0x180071c89  mov     rax, [rax+10h]
0x180071c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071c92  jmp     short loc_180071CC1
0x180071c94  mov     rcx, cs:WPP_GLOBAL_Control
0x180071c9b  lea     rax, WPP_GLOBAL_Control
0x180071ca2  cmp     rcx, rax
0x180071ca5  jz      short loc_180071CC1
0x180071ca7  test    [rcx+1Ch], bl
0x180071caa  jz      short loc_180071CC1
0x180071cac  mov     rcx, [rcx+10h]
0x180071cb0  lea     r8, WPP_8699e7370d6639d67dcf32da8b975182_Traceguids
0x180071cb7  mov     edx, 0Bh
0x180071cbc  call    WPP_SF_d
0x180071cc1  mov     rcx, [rbp+arg_28]
0x180071cc5  mov     rax, [rcx]
0x180071cc8  mov     rax, [rax+10h]
0x180071ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071cd1  mov     eax, edi
0x180071cd3  add     rsp, 40h
0x180071cd7  pop     r15
0x180071cd9  pop     r14
0x180071cdb  pop     r12
0x180071cdd  pop     rdi
0x180071cde  pop     rsi
0x180071cdf  pop     rbx
0x180071ce0  pop     rbp
0x180071ce1  retn
```
