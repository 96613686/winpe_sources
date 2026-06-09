# CEventClass::CreateFromTier2(IEventSystemTier2 *,IUnknown *,ushort const * *,IDispatch * *)

- ea: `0x180015540`
- end: `0x180015738`
- name: `?CreateFromTier2@CEventClass@@SAJPEAUIEventSystemTier2@@PEAUIUnknown@@PEAPEBGPEAPEAUIDispatch@@@Z`
- size: `504`
- prototype: `__int64 __fastcall(struct IEventSystemTier2 *, struct IUnknown *, const unsigned __int16 **, struct IDispatch **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180015540`
- `0x180015740`
- `0x1800157d4`
- `0x180015850`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800155ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800155ea`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800155df`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800155df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015629`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015629`

## pseudocode

```c
__int64 __fastcall CEventClass::CreateFromTier2(
        struct IEventSystemTier2 *a1,
        struct IUnknown *a2,
        const unsigned __int16 **a3,
        struct IDispatch **a4)
{
  __int64 result; // rax
  CEventClass *v7; // rax
  int v8; // ebx
  __int64 v9; // r9
  CEventClass *v10; // rdi
  BYTE *v11; // xmm1_8
  __int128 v12; // xmm0
  BYTE *v13; // xmm1_8
  __int128 v14; // xmm0
  BYTE *v15; // xmm1_8
  int v16; // eax
  struct tagPROPVARIANT v17; // [rsp+40h] [rbp-78h] BYREF
  struct tagPROPVARIANT v18; // [rsp+60h] [rbp-58h] BYREF
  struct tagPROPVARIANT v19; // [rsp+80h] [rbp-38h] BYREF
  IUnknown *pProxy; // [rsp+C8h] [rbp+10h] BYREF

  pProxy = 0;
  *a4 = 0;
  if ( a3 )
    *a3 = 0;
  result = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, IUnknown **))a2->lpVtbl->QueryInterface)(
             a2,
             &IID_IEventClassTier2,
             &pProxy);
  if ( (int)result >= 0 )
  {
    CoSetProxyBlanket(
      pProxy,
      0xFFFFFFFF,
      0xFFFFFFFF,
      (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
      0,
      3u,
      (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
      0x40u);
    v7 = (CEventClass *)CoTaskMemAlloc(0x2D0u);
    if ( v7 && (v10 = CEventClass::CEventClass(v7)) != 0 )
    {
      v8 = ((__int64 (__fastcall *)(IUnknown *, char *))pProxy->lpVtbl[1].AddRef)(pProxy, (char *)v10 + 48);
      if ( v8 < 0 )
        goto LABEL_7;
      v8 = (**(__int64 (__fastcall ***)(CEventClass *, GUID *, struct IDispatch **))v10)(v10, &IID_IEventClass2, a4);
      if ( v8 < 0 )
        goto LABEL_7;
      v11 = (BYTE *)*((_QWORD *)v10 + 44);
      *(_OWORD *)&v17.vt = *((_OWORD *)v10 + 21);
      v12 = *(_OWORD *)((char *)v10 + 312);
      v17.bstrblobVal.pData = v11;
      v13 = (BYTE *)*((_QWORD *)v10 + 41);
      *(_OWORD *)&v18.vt = v12;
      v14 = *((_OWORD *)v10 + 3);
      v18.bstrblobVal.pData = v13;
      v15 = (BYTE *)*((_QWORD *)v10 + 8);
      *(_OWORD *)&v19.vt = v14;
      v19.bstrblobVal.pData = v15;
      v16 = ConcatenateECID_PARTID_APPID(&v19, &v18, &v17, v9, (unsigned __int16 *)v10 + 242);
      v8 = v16;
      if ( a3 )
        *a3 = (const unsigned __int16 *)((char *)v10 + 484);
      *((_DWORD *)v10 + 120) = 0;
      if ( v16 < 0 )
      {
LABEL_7:
        CEventClass::~CEventClass(v10);
        CoTaskMemFree(v10);
      }
    }
    else
    {
      v8 = -2147024882;
    }
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    return (unsigned int)v8;
  }
  return result;
}

```

## disassembly

```asm
0x180015540  push    rsi
0x180015542  push    r14
0x180015544  push    r15
0x180015546  sub     rsp, 0A0h
0x18001554d  xor     r15d, r15d
0x180015550  mov     rsi, r9
0x180015553  mov     [rsp+0B8h+pProxy], r15
0x18001555b  mov     r14, r8
0x18001555e  mov     [r9], r15
0x180015561  mov     r10, rdx
0x180015564  test    r8, r8
0x180015567  jnz     loc_1800156A1
0x18001556d  mov     rax, [rdx]
0x180015570  lea     r8, [rsp+0B8h+pProxy]
0x180015578  lea     rdx, IID_IEventClassTier2
0x18001557f  mov     rcx, r10
0x180015582  mov     rax, [rax]
0x180015585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001558a  test    eax, eax
0x18001558c  js      loc_18001565D
0x180015592  mov     rcx, [rsp+0B8h+pProxy]; pProxy
0x18001559a  mov     edx, 0FFFFFFFFh; dwAuthnSvc
0x18001559f  mov     [rsp+0B8h+dwCapabilities], 40h ; '@'; dwCapabilities
0x1800155a7  mov     r8d, edx; dwAuthzSvc
0x1800155aa  mov     [rsp+0B8h+pAuthInfo], 0FFFFFFFFFFFFFFFFh; pAuthInfo
0x1800155b3  mov     r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1800155ba  mov     [rsp+0B8h+arg_0], rbx
0x1800155c2  mov     [rsp+0B8h+dwImpLevel], 3; dwImpLevel
0x1800155ca  mov     [rsp+0B8h+arg_10], rbp
0x1800155d2  mov     [rsp+0B8h+dwAuthnLevel], r15d; dwAuthnLevel
0x1800155d7  mov     [rsp+0B8h+arg_18], rdi
0x1800155df  call    cs:__imp_CoSetProxyBlanket
0x1800155e5  mov     ecx, 2D0h; cb
0x1800155ea  call    cs:__imp_CoTaskMemAlloc
0x1800155f0  test    rax, rax
0x1800155f3  jnz     short loc_18001566A
0x1800155f5  mov     ebx, 8007000Eh
0x1800155fa  jmp     short loc_18001562F
0x1800155fc  mov     rax, [rdi]
0x1800155ff  lea     rdx, IID_IEventClass2
0x180015606  mov     r8, rsi
0x180015609  mov     rcx, rdi
0x18001560c  mov     rax, [rax]
0x18001560f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015614  mov     ebx, eax
0x180015616  test    eax, eax
0x180015618  jns     loc_1800156A9
0x18001561e  mov     rcx, rdi; this
0x180015621  call    ??1CEventClass@@AEAA@XZ; CEventClass::~CEventClass(void)
0x180015626  mov     rcx, rdi; pv
0x180015629  call    cs:__imp_CoTaskMemFree
0x18001562f  mov     rcx, [rsp+0B8h+pProxy]
0x180015637  mov     rax, [rcx]
0x18001563a  mov     rax, [rax+10h]
0x18001563e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015643  mov     rdi, [rsp+0B8h+arg_18]
0x18001564b  mov     eax, ebx
0x18001564d  mov     rbx, [rsp+0B8h+arg_0]
0x180015655  mov     rbp, [rsp+0B8h+arg_10]
0x18001565d  add     rsp, 0A0h
0x180015664  pop     r15
0x180015666  pop     r14
0x180015668  pop     rsi
0x180015669  retn
0x18001566a  mov     rcx, rax; this
0x18001566d  call    ??0CEventClass@@AEAA@XZ; CEventClass::CEventClass(void)
0x180015672  mov     rdi, rax
0x180015675  test    rax, rax
0x180015678  jz      loc_1800155F5
0x18001567e  mov     rcx, [rsp+0B8h+pProxy]
0x180015686  mov     rdx, [rcx]
0x180015689  mov     rax, [rdx+20h]
0x18001568d  lea     rdx, [rdi+30h]
0x180015691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015696  mov     ebx, eax
0x180015698  test    eax, eax
0x18001569a  js      short loc_18001561E
0x18001569c  jmp     loc_1800155FC
0x1800156a1  mov     [r8], r15
0x1800156a4  jmp     loc_18001556D
0x1800156a9  movups  xmm0, xmmword ptr [rdi+150h]
0x1800156b0  lea     rsi, [rdi+1E4h]
0x1800156b7  movsd   xmm1, qword ptr [rdi+160h]
0x1800156bf  lea     r8, [rsp+0B8h+var_78]; struct tagPROPVARIANT *
0x1800156c4  movaps  xmmword ptr [rsp+0B8h+var_78], xmm0
0x1800156c9  lea     rdx, [rsp+0B8h+var_58]; struct tagPROPVARIANT *
0x1800156ce  movups  xmm0, xmmword ptr [rdi+138h]
0x1800156d5  lea     rcx, [rsp+0B8h+var_38]; struct tagPROPVARIANT *
0x1800156dd  mov     qword ptr [rsp+0B8h+dwAuthnLevel], rsi; unsigned __int16 *
0x1800156e2  movsd   qword ptr [rsp+0B8h+var_78+10h], xmm1
0x1800156e8  movsd   xmm1, qword ptr [rdi+148h]
0x1800156f0  movaps  xmmword ptr [rsp+0B8h+var_58], xmm0
0x1800156f5  movups  xmm0, xmmword ptr [rdi+30h]
0x1800156f9  movsd   qword ptr [rsp+0B8h+var_58+10h], xmm1
0x1800156ff  movsd   xmm1, qword ptr [rdi+40h]
0x180015704  movaps  xmmword ptr [rsp+0B8h+var_38], xmm0
0x18001570c  movsd   qword ptr [rsp+0B8h+var_38+10h], xmm1
0x180015715  call    ?ConcatenateECID_PARTID_APPID@@YAJUtagPROPVARIANT@@00KPEAG@Z; ConcatenateECID_PARTID_APPID(tagPROPVARIANT,tagPROPVARIANT,tagPROPVARIANT,ulong,ushort *)
0x18001571a  mov     ebx, eax
0x18001571c  test    r14, r14
0x18001571f  jz      short loc_180015724
0x180015721  mov     [r14], rsi
0x180015724  mov     [rdi+1E0h], r15d
0x18001572b  test    eax, eax
0x18001572d  jns     loc_18001562F
0x180015733  jmp     loc_18001561E
```
