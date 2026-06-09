# CPropertyStoreOverFolder::_GetExpandoProperties(CPropertyStoreOverFolder *,_ITEMID_CHILD const *,tagPROPVARIANT *,int,ushort * *)

- ea: `0x18006bb30`
- end: `0x18006bc4b`
- name: `?_GetExpandoProperties@CPropertyStoreOverFolder@@CAJPEAV1@PEFBU_ITEMID_CHILD@@PEAUtagPROPVARIANT@@HPEAPEAG@Z`
- size: `283`
- prototype: `__int64 __fastcall(struct CPropertyStoreOverFolder *, const struct _ITEMID_CHILD *, struct tagPROPVARIANT *, int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18001a3fc`
- `0x18002d070`
- `0x18006bb30`
- `0x18006ed20`
- `0x18007f3d4`
- `0x18007f4bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bc22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bc22`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18006bba9`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18006bba9`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x18006bbd9`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x18006bbd9`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CPropertyStoreOverFolder::_GetExpandoProperties(
        struct CPropertyStoreOverFolder *a1,
        const struct _ITEMID_CHILD *a2,
        struct tagPROPVARIANT *a3,
        __int64 a4,
        unsigned __int16 **a5)
{
  __int64 v7; // rcx
  int PropStoreFromIDList; // ebx
  __int64 v9; // r8
  struct IStream *v10; // rax
  IStream *v11; // rdi
  unsigned __int16 *v12; // rax
  struct IStream *v14; // [rsp+20h] [rbp-30h] BYREF
  LPVOID pv[3]; // [rsp+28h] [rbp-28h] BYREF
  struct IUnknown *v16; // [rsp+40h] [rbp-10h] BYREF

  pv[0] = 0;
  pv[1] = (LPVOID)-1LL;
  pv[2] = (LPVOID)-1LL;
  PropStoreFromIDList = _AllocString<CTCoAllocPolicy>(a1, a2, L"PropStoreOverFolder", pv);
  if ( PropStoreFromIDList >= 0 )
  {
    v16 = 0;
    PropStoreFromIDList = HiddenProperties_GetPropStoreFromIDList(v7, a2, v9, &v16);
    if ( PropStoreFromIDList >= 0 )
    {
      v10 = SHCreateMemStream(0, 0);
      v11 = v10;
      v14 = v10;
      if ( v10 )
      {
        PropStoreFromIDList = IUnknown_SaveToStream(v10, 0, v16);
        if ( PropStoreFromIDList >= 0 )
        {
          IStream_Reset(v11);
          a3->vt = 66;
          v14 = 0;
          a3->hVal.QuadPart = (LONGLONG)v11;
          if ( a5 )
          {
            v12 = (unsigned __int16 *)pv[0];
            pv[0] = 0;
            *a5 = v12;
          }
        }
      }
      else
      {
        PropStoreFromIDList = -2147024882;
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
  }
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  return (unsigned int)PropStoreFromIDList;
}

```

## disassembly

```asm
0x18006bb30  mov     [rsp-18h+arg_0], rbx
0x18006bb35  mov     [rsp-18h+arg_18], rsi
0x18006bb3a  push    rbp
0x18006bb3b  push    rdi
0x18006bb3c  push    r14
0x18006bb3e  mov     rbp, rsp
0x18006bb41  sub     rsp, 50h
0x18006bb45  mov     rax, cs:__security_cookie
0x18006bb4c  xor     rax, rsp
0x18006bb4f  mov     [rbp+var_8], rax
0x18006bb53  mov     r14, r8
0x18006bb56  mov     rdi, rdx
0x18006bb59  mov     rsi, [rbp+arg_20]
0x18006bb5d  mov     [rbp+pv], 0
0x18006bb65  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006bb69  mov     [rbp+var_20], rax
0x18006bb6d  mov     [rbp+var_18], rax
0x18006bb71  lea     r9, [rbp+pv]
0x18006bb75  lea     r8, aPropstoreoverf_0; "PropStoreOverFolder"
0x18006bb7c  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18006bb81  mov     ebx, eax
0x18006bb83  test    eax, eax
0x18006bb85  js      loc_18006BC19
0x18006bb8b  mov     [rbp+var_10], 0
0x18006bb93  lea     r9, [rbp+var_10]
0x18006bb97  mov     rdx, rdi
0x18006bb9a  call    ?HiddenProperties_GetPropStoreFromIDList@@YAJW4IDLHID@@PEBU_ITEMIDLIST_RELATIVE@@AEBU_GUID@@PEAPEAX@Z; HiddenProperties_GetPropStoreFromIDList(IDLHID,_ITEMIDLIST_RELATIVE const *,_GUID const &,void * *)
0x18006bb9f  mov     ebx, eax
0x18006bba1  test    eax, eax
0x18006bba3  js      short loc_18006BC0F
0x18006bba5  xor     edx, edx; cbInit
0x18006bba7  xor     ecx, ecx; pInit
0x18006bba9  call    cs:__imp_SHCreateMemStream
0x18006bbaf  mov     rdi, rax
0x18006bbb2  mov     [rbp+var_30], rax
0x18006bbb6  test    rax, rax
0x18006bbb9  jnz     short loc_18006BBC2
0x18006bbbb  mov     ebx, 8007000Eh
0x18006bbc0  jmp     short loc_18006BC05
0x18006bbc2  mov     r8, [rbp+var_10]; struct IUnknown *
0x18006bbc6  xor     edx, edx; int
0x18006bbc8  mov     rcx, rdi; struct IStream *
0x18006bbcb  call    ?IUnknown_SaveToStream@@YAJPEAUIStream@@HPEAUIUnknown@@@Z; IUnknown_SaveToStream(IStream *,int,IUnknown *)
0x18006bbd0  mov     ebx, eax
0x18006bbd2  test    eax, eax
0x18006bbd4  js      short loc_18006BC05
0x18006bbd6  mov     rcx, rdi; pstm
0x18006bbd9  call    cs:__imp_IStream_Reset
0x18006bbdf  mov     word ptr [r14], 42h ; 'B'
0x18006bbe5  mov     [rbp+var_30], 0
0x18006bbed  mov     [r14+8], rdi
0x18006bbf1  test    rsi, rsi
0x18006bbf4  jz      short loc_18006BC05
0x18006bbf6  mov     rax, [rbp+pv]
0x18006bbfa  mov     [rbp+pv], 0
0x18006bc02  mov     [rsi], rax
0x18006bc05  lea     rcx, [rbp+var_30]
0x18006bc09  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006bc0e  nop
0x18006bc0f  lea     rcx, [rbp+var_10]
0x18006bc13  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006bc18  nop
0x18006bc19  mov     rcx, [rbp+pv]; pv
0x18006bc1d  test    rcx, rcx
0x18006bc20  jz      short loc_18006BC28
0x18006bc22  call    cs:__imp_CoTaskMemFree
0x18006bc28  mov     eax, ebx
0x18006bc2a  mov     rcx, [rbp+var_8]
0x18006bc2e  xor     rcx, rsp; StackCookie
0x18006bc31  call    __security_check_cookie
0x18006bc36  lea     r11, [rsp+50h+var_s0]
0x18006bc3b  mov     rbx, [r11+20h]
0x18006bc3f  mov     rsi, [r11+38h]
0x18006bc43  mov     rsp, r11
0x18006bc46  pop     r14
0x18006bc48  pop     rdi
0x18006bc49  pop     rbp
0x18006bc4a  retn
```
