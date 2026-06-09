# CMSMQMessage::GetStoredObject(tagVARIANT *)

- ea: `0x1800155cc`
- end: `0x18001580f`
- name: `?GetStoredObject@CMSMQMessage@@IEAAJPEAUtagVARIANT@@@Z`
- size: `579`
- prototype: `int(CMSMQMessage *__hidden this, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800180f0`

## callees

- `0x18000cb34`
- `0x1800154cc`
- `0x1800155cc`
- `0x1800273b0`
- `0x180029010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001567e`
- `KERNEL32!GetLastError` at `0x18001567e`
- `KERNEL32!GlobalLock` at `0x180015648`
- `KERNEL32!GlobalLock` at `0x180015648`
- `KERNEL32!GlobalUnlock` at `0x180015674`
- `KERNEL32!GlobalUnlock` at `0x180015674`
- `ole32!ReadClassStg` at `0x180015696`
- `ole32!ReadClassStg` at `0x180015696`
- `ole32!CoCreateInstance` at `0x1800156c0`
- `ole32!CoCreateInstance` at `0x1800156c0`
- `OLEAUT32!__imp_VariantClear` at `0x180015612`
- `OLEAUT32!__imp_VariantClear` at `0x180015612`

## pseudocode

```c
__int64 __fastcall CMSMQMessage::GetStoredObject(CMSMQMessage *this, struct tagVARIANT *a2)
{
  LPSTORAGE v3; // rdi
  CMSMQMessage *v5; // rcx
  HRESULT StorageOfBody; // ebx
  LPVOID v7; // rax
  void *v8; // rcx
  LONGLONG v9; // rcx
  LONGLONG v10; // rcx
  LONGLONG v12; // [rsp+30h] [rbp-40h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-38h] BYREF
  LPSTORAGE pStg; // [rsp+40h] [rbp-30h] BYREF
  LONGLONG v15; // [rsp+48h] [rbp-28h] BYREF
  CLSID pclsid; // [rsp+50h] [rbp-20h] BYREF

  v12 = 0;
  v3 = 0;
  v15 = 0;
  pStg = 0;
  ppv = 0;
  VariantClear(a2);
  if ( !*((_QWORD *)this + 30) )
  {
    a2->vt = 10;
    goto LABEL_19;
  }
  StorageOfBody = CMSMQMessage::GetStorageOfBody(v5, *((_DWORD *)this + 62), *((void **)this + 28), &pStg);
  if ( StorageOfBody < 0 )
  {
LABEL_5:
    v3 = pStg;
    goto LABEL_20;
  }
  v7 = GlobalLock(*((HGLOBAL *)this + 30));
  *((_QWORD *)this + 28) = v7;
  if ( !v7 )
  {
    StorageOfBody = -2147024882;
    goto LABEL_5;
  }
  v8 = (void *)*((_QWORD *)this + 30);
  if ( v8 && !GlobalUnlock(v8) )
    GetLastError();
  v3 = pStg;
  pclsid = 0;
  StorageOfBody = ReadClassStg(pStg, &pclsid);
  if ( StorageOfBody >= 0 )
  {
    StorageOfBody = CoCreateInstance(&pclsid, 0, 0x15u, &IID_IPersistStorage, &ppv);
    if ( StorageOfBody >= 0 )
    {
      StorageOfBody = (*(__int64 (__fastcall **)(LPVOID, LPSTORAGE))(*(_QWORD *)ppv + 48LL))(ppv, v3);
      if ( StorageOfBody >= 0 )
      {
        StorageOfBody = (**(__int64 (__fastcall ***)(LPVOID, GUID *, LONGLONG *))ppv)(ppv, &IID_IUnknown, &v12);
        if ( StorageOfBody >= 0 )
        {
          StorageOfBody = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, LONGLONG *))v12)(v12, &IID_IDispatch, &v15);
          if ( StorageOfBody >= 0 )
          {
            v9 = v15;
            a2->vt = 9;
            a2->llVal = v9;
            if ( v9 )
              (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v9 + 8LL))(v9);
            goto LABEL_20;
          }
          v10 = v12;
          a2->vt = 13;
          a2->llVal = v10;
          if ( v10 )
            (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v10 + 8LL))(v10);
LABEL_19:
          StorageOfBody = 0;
        }
      }
    }
  }
LABEL_20:
  if ( v12 )
  {
    (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( v3 )
    ((void (__fastcall *)(LPSTORAGE))v3->lpVtbl->Release)(v3);
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v15 )
  {
    (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  return CreateErrorHelper((unsigned int)StorageOfBody, 1);
}

```

## disassembly

```asm
0x1800155cc  mov     [rsp-18h+arg_10], rbx
0x1800155d1  mov     [rsp-18h+arg_18], rsi
0x1800155d6  push    rbp
0x1800155d7  push    rdi
0x1800155d8  push    r14
0x1800155da  mov     rbp, rsp
0x1800155dd  sub     rsp, 70h
0x1800155e1  mov     rax, cs:__security_cookie
0x1800155e8  xor     rax, rsp
0x1800155eb  mov     [rbp+var_10], rax
0x1800155ef  mov     rsi, rcx
0x1800155f2  mov     [rbp+var_40], 0
0x1800155fa  xor     edi, edi
0x1800155fc  mov     [rbp+var_28], 0
0x180015604  mov     rcx, rdx; pvarg
0x180015607  mov     [rbp+pStg], rdi
0x18001560b  mov     [rbp+var_38], rdi
0x18001560f  mov     r14, rdx
0x180015612  call    cs:__imp_VariantClear
0x180015618  cmp     [rsi+0F0h], rdi
0x18001561f  jz      loc_18001576F
0x180015625  mov     r8, [rsi+0E0h]; void *
0x18001562c  lea     r9, [rbp+pStg]; struct IStorage **
0x180015630  mov     edx, [rsi+0F8h]; unsigned int
0x180015636  call    ?GetStorageOfBody@CMSMQMessage@@IEAAJKPEAXPEAPEAUIStorage@@@Z; CMSMQMessage::GetStorageOfBody(ulong,void *,IStorage * *)
0x18001563b  mov     ebx, eax
0x18001563d  test    eax, eax
0x18001563f  js      short loc_18001565F
0x180015641  mov     rcx, [rsi+0F0h]; hMem
0x180015648  call    cs:__imp_GlobalLock
0x18001564e  mov     [rsi+0E0h], rax
0x180015655  test    rax, rax
0x180015658  jnz     short loc_180015668
0x18001565a  mov     ebx, 8007000Eh
0x18001565f  mov     rdi, [rbp+pStg]
0x180015663  jmp     loc_180015777
0x180015668  mov     rcx, [rsi+0F0h]; hMem
0x18001566f  test    rcx, rcx
0x180015672  jz      short loc_180015684
0x180015674  call    cs:__imp_GlobalUnlock
0x18001567a  test    eax, eax
0x18001567c  jnz     short loc_180015684
0x18001567e  call    cs:__imp_GetLastError
0x180015684  mov     rdi, [rbp+pStg]
0x180015688  lea     rdx, [rbp+pclsid]; pclsid
0x18001568c  xorps   xmm0, xmm0
0x18001568f  mov     rcx, rdi; pStg
0x180015692  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x180015696  call    cs:__imp_ReadClassStg
0x18001569c  mov     ebx, eax
0x18001569e  test    eax, eax
0x1800156a0  js      loc_180015777
0x1800156a6  xor     edx, edx; pUnkOuter
0x1800156a8  lea     rax, [rbp+var_38]
0x1800156ac  lea     r9, IID_IPersistStorage; riid
0x1800156b3  mov     [rsp+70h+ppv], rax; ppv
0x1800156b8  lea     rcx, [rbp+pclsid]; rclsid
0x1800156bc  lea     r8d, [rdx+15h]; dwClsContext
0x1800156c0  call    cs:__imp_CoCreateInstance
0x1800156c6  mov     ebx, eax
0x1800156c8  test    eax, eax
0x1800156ca  js      loc_180015777
0x1800156d0  mov     rcx, [rbp+var_38]
0x1800156d4  mov     rdx, rdi
0x1800156d7  mov     rax, [rcx]
0x1800156da  mov     rax, [rax+30h]
0x1800156de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156e3  mov     ebx, eax
0x1800156e5  test    eax, eax
0x1800156e7  js      loc_180015777
0x1800156ed  mov     rcx, [rbp+var_38]
0x1800156f1  lea     r8, [rbp+var_40]
0x1800156f5  lea     rdx, IID_IUnknown
0x1800156fc  mov     rax, [rcx]
0x1800156ff  mov     rax, [rax]
0x180015702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015707  mov     ebx, eax
0x180015709  test    eax, eax
0x18001570b  js      short loc_180015777
0x18001570d  mov     rcx, [rbp+var_40]
0x180015711  lea     r8, [rbp+var_28]
0x180015715  lea     rdx, IID_IDispatch
0x18001571c  mov     rax, [rcx]
0x18001571f  mov     rax, [rax]
0x180015722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015727  mov     ebx, eax
0x180015729  test    eax, eax
0x18001572b  js      short loc_18001574E
0x18001572d  mov     rcx, [rbp+var_28]
0x180015731  mov     word ptr [r14], 9
0x180015737  mov     [r14+8], rcx
0x18001573b  test    rcx, rcx
0x18001573e  jz      short loc_180015777
0x180015740  mov     rax, [rcx]
0x180015743  mov     rax, [rax+8]
0x180015747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001574c  jmp     short loc_180015777
0x18001574e  mov     rcx, [rbp+var_40]
0x180015752  mov     word ptr [r14], 0Dh
0x180015758  mov     [r14+8], rcx
0x18001575c  test    rcx, rcx
0x18001575f  jz      short loc_180015775
0x180015761  mov     rax, [rcx]
0x180015764  mov     rax, [rax+8]
0x180015768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001576d  jmp     short loc_180015775
0x18001576f  mov     word ptr [r14], 0Ah
0x180015775  xor     ebx, ebx
0x180015777  mov     rcx, [rbp+var_40]
0x18001577b  test    rcx, rcx
0x18001577e  jz      short loc_180015794
0x180015780  mov     rax, [rcx]
0x180015783  mov     rax, [rax+10h]
0x180015787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001578c  mov     [rbp+var_40], 0
0x180015794  test    rdi, rdi
0x180015797  jz      short loc_1800157A8
0x180015799  mov     rax, [rdi]
0x18001579c  mov     rcx, rdi
0x18001579f  mov     rax, [rax+10h]
0x1800157a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157a8  mov     rcx, [rbp+var_38]
0x1800157ac  test    rcx, rcx
0x1800157af  jz      short loc_1800157C5
0x1800157b1  mov     rax, [rcx]
0x1800157b4  mov     rax, [rax+10h]
0x1800157b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157bd  mov     [rbp+var_38], 0
0x1800157c5  mov     rcx, [rbp+var_28]
0x1800157c9  test    rcx, rcx
0x1800157cc  jz      short loc_1800157E2
0x1800157ce  mov     rax, [rcx]
0x1800157d1  mov     rax, [rax+10h]
0x1800157d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157da  mov     [rbp+var_28], 0
0x1800157e2  mov     edx, 1
0x1800157e7  mov     ecx, ebx
0x1800157e9  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x1800157ee  mov     rcx, [rbp+var_10]
0x1800157f2  xor     rcx, rsp; StackCookie
0x1800157f5  call    __security_check_cookie
0x1800157fa  lea     r11, [rsp+70h+var_s0]
0x1800157ff  mov     rbx, [r11+30h]
0x180015803  mov     rsi, [r11+38h]
0x180015807  mov     rsp, r11
0x18001580a  pop     r14
0x18001580c  pop     rdi
0x18001580d  pop     rbp
0x18001580e  retn
```
