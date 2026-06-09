# PublicNetworkConnection::GetConnectionId(_GUID *)

- ea: `0x180032b60`
- end: `0x180032cba`
- name: `?GetConnectionId@PublicNetworkConnection@@UEAAJPEAU_GUID@@@Z`
- size: `346`
- prototype: `__int64 __fastcall(PublicNetworkConnection *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006770`
- `0x180006810`
- `0x1800068d0`
- `0x180008660`
- `0x1800086b0`
- `0x1800120d0`
- `0x180032b60`
- `0x180033404`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032c5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032c5e`

## pseudocode

```c
__int64 __fastcall PublicNetworkConnection::GetConnectionId(PublicNetworkConnection *this, struct _GUID *a2)
{
  PVOID *v4; // rcx
  int PrivateNetworkInterface; // ebx
  struct _GUID v7; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v8; // [rsp+40h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-18h] BYREF
  struct INetworkInterfacePrivate *v10; // [rsp+50h] [rbp-10h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_cbe8f8d8b9e533271e4839292fb068f7_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    *a2 = GUID_NULL;
    v10 = 0;
    PrivateNetworkInterface = PublicNetworkConnection::GetPrivateNetworkInterface(this, &v10);
    if ( PrivateNetworkInterface >= 0 )
    {
      v8 = 0;
      pv = 0;
      PrivateNetworkInterface = (*(__int64 (__fastcall **)(struct INetworkInterfacePrivate *, unsigned int *, LPVOID *))(*(_QWORD *)v10 + 24LL))(
                                  v10,
                                  &v8,
                                  &pv);
      if ( PrivateNetworkInterface >= 0 )
      {
        *a2 = *GetConnectionIdFromInterfaceByteBlob(&v7, v8, (const unsigned __int8 *)pv);
        CoTaskMemFree(pv);
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF__guid_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        WPP_cbe8f8d8b9e533271e4839292fb068f7_Traceguids,
        a2,
        PrivateNetworkInterface);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v10);
  }
  else
  {
    PrivateNetworkInterface = -2147467261;
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
      WPP_SF_d(v4[2], 28, WPP_cbe8f8d8b9e533271e4839292fb068f7_Traceguids, 2147500035LL);
  }
  return (unsigned int)PrivateNetworkInterface;
}

```

## disassembly

```asm
0x180032b60  mov     [rsp-18h+arg_10], rbx
0x180032b65  push    rbp
0x180032b66  push    rdi
0x180032b67  push    r15
0x180032b69  mov     rbp, rsp
0x180032b6c  sub     rsp, 60h
0x180032b70  mov     rax, cs:__security_cookie
0x180032b77  xor     rax, rsp
0x180032b7a  mov     [rbp+var_8], rax
0x180032b7e  mov     rdi, rdx
0x180032b81  mov     rbx, rcx
0x180032b84  lea     r15, WPP_GLOBAL_Control
0x180032b8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180032b92  cmp     rcx, r15
0x180032b95  jz      short loc_180032BB9
0x180032b97  test    byte ptr [rcx+1Ch], 8
0x180032b9b  jz      short loc_180032BB9
0x180032b9d  mov     edx, 1Bh
0x180032ba2  lea     r8, WPP_cbe8f8d8b9e533271e4839292fb068f7_Traceguids
0x180032ba9  mov     rcx, [rcx+10h]
0x180032bad  call    WPP_SF_
0x180032bb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180032bb9  test    rdi, rdi
0x180032bbc  jnz     short loc_180032BF1
0x180032bbe  mov     ebx, 80004003h
0x180032bc3  cmp     rcx, r15
0x180032bc6  jz      loc_180032C9B
0x180032bcc  test    byte ptr [rcx+1Ch], 8
0x180032bd0  jz      loc_180032C9B
0x180032bd6  lea     edx, [rdi+1Ch]
0x180032bd9  mov     r9d, ebx
0x180032bdc  lea     r8, WPP_cbe8f8d8b9e533271e4839292fb068f7_Traceguids
0x180032be3  mov     rcx, [rcx+10h]
0x180032be7  call    WPP_SF_d
0x180032bec  jmp     loc_180032C9B
0x180032bf1  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180032bf8  movdqu  xmmword ptr [rdi], xmm0
0x180032bfc  mov     [rbp+var_10], 0
0x180032c04  lea     rdx, [rbp+var_10]; struct INetworkInterfacePrivate **
0x180032c08  mov     rcx, rbx; this
0x180032c0b  call    ?GetPrivateNetworkInterface@PublicNetworkConnection@@AEBAJPEAPEAUINetworkInterfacePrivate@@@Z; PublicNetworkConnection::GetPrivateNetworkInterface(INetworkInterfacePrivate * *)
0x180032c10  mov     ebx, eax
0x180032c12  test    eax, eax
0x180032c14  js      short loc_180032C64
0x180032c16  mov     [rbp+var_20], 0
0x180032c1d  mov     [rbp+pv], 0
0x180032c25  mov     rcx, [rbp+var_10]
0x180032c29  mov     rax, [rcx]
0x180032c2c  lea     r8, [rbp+pv]
0x180032c30  lea     rdx, [rbp+var_20]
0x180032c34  mov     rax, [rax+18h]
0x180032c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032c3d  mov     ebx, eax
0x180032c3f  test    eax, eax
0x180032c41  js      short loc_180032C64
0x180032c43  mov     r8, [rbp+pv]; unsigned __int8 *
0x180032c47  mov     edx, [rbp+var_20]; unsigned int
0x180032c4a  lea     rcx, [rbp+var_30]; retstr
0x180032c4e  call    ?GetConnectionIdFromInterfaceByteBlob@@YA?AU_GUID@@KPEBE@Z; GetConnectionIdFromInterfaceByteBlob(ulong,uchar const *)
0x180032c53  movups  xmm1, xmmword ptr [rax]
0x180032c56  movdqu  xmmword ptr [rdi], xmm1
0x180032c5a  mov     rcx, [rbp+pv]; pv
0x180032c5e  call    cs:__imp_CoTaskMemFree
0x180032c64  mov     rcx, cs:WPP_GLOBAL_Control
0x180032c6b  cmp     rcx, r15
0x180032c6e  jz      short loc_180032C92
0x180032c70  test    byte ptr [rcx+1Ch], 8
0x180032c74  jz      short loc_180032C92
0x180032c76  mov     edx, 1Dh
0x180032c7b  mov     [rsp+60h+var_40], ebx
0x180032c7f  mov     r9, rdi
0x180032c82  lea     r8, WPP_cbe8f8d8b9e533271e4839292fb068f7_Traceguids
0x180032c89  mov     rcx, [rcx+10h]
0x180032c8d  call    WPP_SF__guid_d
0x180032c92  lea     rcx, [rbp+var_10]
0x180032c96  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032c9b  mov     eax, ebx
0x180032c9d  mov     rcx, [rbp+var_8]
0x180032ca1  xor     rcx, rsp; StackCookie
0x180032ca4  call    __security_check_cookie
0x180032ca9  mov     rbx, [rsp+60h+arg_10]
0x180032cb1  add     rsp, 60h
0x180032cb5  pop     r15
0x180032cb7  pop     rdi
0x180032cb8  pop     rbp
0x180032cb9  retn
```
