# CDataTransferObj::GetDataForEmbeddedObject(IOleObject *,IStorage *)

- ea: `0x18005c608`
- end: `0x18005c7f7`
- name: `?GetDataForEmbeddedObject@CDataTransferObj@@AEAAPEAUIStorage@@PEAUIOleObject@@PEAU2@@Z`
- size: `495`
- prototype: `struct IStorage *__fastcall(CDataTransferObj *__hidden this, struct IOleObject *, struct IStorage *)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18005bc58`
- `0x18005c340`
- `0x18005c608`
- `0x18005c800`

## callees

- `0x1800427ac`
- `0x18005c608`
- `0x1800928dc`
- `0x1800931b0`
- `0x180095010`

## string_xrefs

- `0x18005c70c`: `StgCreateDocfileOnILockBytes`
- `0x18005c6c1`: `CreateILockBytesOnHGlobal`

## pseudocode

```c
struct IStorage *__fastcall CDataTransferObj::GetDataForEmbeddedObject(
        CDataTransferObj *this,
        struct IOleObject *a2,
        struct IStorage *a3)
{
  __int64 *v4; // rcx
  __int64 v5; // rax
  struct COLE32_PROC *Ole32Procs; // rax
  _QWORD *v8; // rbx
  __int64 v9; // rsi
  struct COLE32_PROC *v10; // rax
  struct COLE32_PROC *v11; // rbx
  int v12; // ebx
  struct IPersistStorage *v13; // rcx
  struct IStorage *v14; // rdx
  int v15; // ebx
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  struct IStorage *DataForEmbeddedObject; // rax
  struct IPersistStorage *v21; // rcx
  struct IPersistStorage *v22; // [rsp+50h] [rbp+20h] BYREF
  struct IStorage *v23; // [rsp+60h] [rbp+30h] BYREF
  __int64 v24; // [rsp+68h] [rbp+38h] BYREF

  v23 = a3;
  v22 = 0;
  v4 = (__int64 *)*((_QWORD *)this + 13);
  if ( v4 )
  {
    v5 = *v4;
    if ( !a3 )
    {
      (*(void (__fastcall **)(__int64 *, struct IOleObject *, _QWORD, struct IOleObject *))(v5 + 8))(v4, a2, 0, a2);
      return (struct IStorage *)*((_QWORD *)this + 13);
    }
    if ( !(*(unsigned int (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, struct IStorage *))(v5 + 56))(
            v4,
            0,
            0,
            0,
            a3) )
    {
      ((void (__fastcall *)(struct IStorage *, _QWORD))v23->lpVtbl->Commit)(v23, 0);
      return (struct IStorage *)*((_QWORD *)this + 13);
    }
    return 0;
  }
  if ( ((__int64 (__fastcall *)(struct IOleObject *, GUID *, struct IPersistStorage **))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IPersistStorage,
         &v22) )
  {
    return 0;
  }
  if ( !v23 )
  {
    v24 = 0;
    Ole32Procs = CThreadData::GetOle32Procs();
    v8 = (_QWORD *)((char *)Ole32Procs + 80);
    if ( !*((_QWORD *)Ole32Procs + 10) )
      SetProcAddr((FARPROC *)Ole32Procs + 10, 1, "CreateILockBytesOnHGlobal");
    if ( !*v8 || ((unsigned int (__fastcall *)(_QWORD, __int64, __int64 *))*v8)(0, 1, &v24) )
    {
      v13 = v22;
    }
    else
    {
      v9 = v24;
      v10 = CThreadData::GetOle32Procs();
      v11 = (struct COLE32_PROC *)((char *)v10 + 72);
      if ( !*((_QWORD *)v10 + 9) )
        SetProcAddr((FARPROC *)v10 + 9, 1, "StgCreateDocfileOnILockBytes");
      if ( *(_QWORD *)v11 )
        v12 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, struct IStorage **))v11)(v9, 69650, 0, &v23);
      else
        v12 = -2147467259;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      v13 = v22;
      if ( !v12 )
      {
        v14 = v23;
        *((_QWORD *)this + 13) = v23;
        v15 = CW32System::OleSave(v13, v14, 0);
        v16 = ((__int64 (__fastcall *)(struct IPersistStorage *, _QWORD))v22->lpVtbl->SaveCompleted)(v22, 0);
        if ( v15 || v16 )
          v23 = 0;
        ((void (__fastcall *)(struct IPersistStorage *, __int64, __int64, __int64))v22->lpVtbl->Release)(
          v22,
          v17,
          v18,
          v19);
        return (struct IStorage *)*((_QWORD *)this + 13);
      }
    }
    ((void (__fastcall *)(struct IPersistStorage *))v13->lpVtbl->Release)(v13);
    return 0;
  }
  DataForEmbeddedObject = CDataTransferObj::GetDataForEmbeddedObject(this, *((struct IOleObject **)this + 12), 0);
  v21 = v22;
  *((_QWORD *)this + 13) = DataForEmbeddedObject;
  ((void (__fastcall *)(struct IPersistStorage *))v21->lpVtbl->Release)(v21);
  return CDataTransferObj::GetDataForEmbeddedObject(this, *((struct IOleObject **)this + 12), v23);
}

```

## disassembly

```asm
0x18005c608  mov     [rsp-18h+arg_8], rbx
0x18005c60d  mov     [rsp-18h+arg_10], r8
0x18005c612  push    rbp
0x18005c613  push    rsi
0x18005c614  push    rdi
0x18005c615  mov     rbp, rsp
0x18005c618  sub     rsp, 30h
0x18005c61c  mov     rdi, rcx
0x18005c61f  mov     [rbp+arg_0], 0
0x18005c627  mov     rcx, [rcx+68h]
0x18005c62b  mov     r9, rdx
0x18005c62e  test    rcx, rcx
0x18005c631  jz      short loc_18005C67B
0x18005c633  mov     rax, [rcx]
0x18005c636  test    r8, r8
0x18005c639  jz      short loc_18005C670
0x18005c63b  mov     rax, [rax+38h]
0x18005c63f  xor     r9d, r9d
0x18005c642  mov     [rsp+30h+var_10], r8
0x18005c647  xor     edx, edx
0x18005c649  xor     r8d, r8d
0x18005c64c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c651  test    eax, eax
0x18005c653  jnz     short loc_18005C698
0x18005c655  mov     rcx, [rbp+arg_10]
0x18005c659  xor     edx, edx
0x18005c65b  mov     rax, [rcx]
0x18005c65e  mov     rax, [rax+48h]
0x18005c662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c667  mov     rax, [rdi+68h]
0x18005c66b  jmp     loc_18005C7E9
0x18005c670  mov     rax, [rax+8]
0x18005c674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c679  jmp     short loc_18005C667
0x18005c67b  mov     rax, [rdx]
0x18005c67e  lea     r8, [rbp+arg_0]
0x18005c682  lea     rdx, IID_IPersistStorage
0x18005c689  mov     rcx, r9
0x18005c68c  mov     rax, [rax]
0x18005c68f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c694  test    eax, eax
0x18005c696  jz      short loc_18005C69F
0x18005c698  xor     eax, eax
0x18005c69a  jmp     loc_18005C7E9
0x18005c69f  cmp     [rbp+arg_10], 0
0x18005c6a4  jnz     loc_18005C7B6
0x18005c6aa  mov     [rbp+arg_18], 0
0x18005c6b2  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x18005c6b7  lea     rbx, [rax+50h]
0x18005c6bb  cmp     qword ptr [rbx], 0
0x18005c6bf  jnz     short loc_18005C6D5
0x18005c6c1  lea     r8, aCreateilockbyt; "CreateILockBytesOnHGlobal"
0x18005c6c8  mov     edx, 1
0x18005c6cd  mov     rcx, rbx
0x18005c6d0  call    SetProcAddr
0x18005c6d5  mov     rax, [rbx]
0x18005c6d8  test    rax, rax
0x18005c6db  jz      loc_18005C7A1
0x18005c6e1  lea     r8, [rbp+arg_18]
0x18005c6e5  mov     edx, 1
0x18005c6ea  xor     ecx, ecx
0x18005c6ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c6f1  test    eax, eax
0x18005c6f3  jnz     loc_18005C7A1
0x18005c6f9  mov     rsi, [rbp+arg_18]
0x18005c6fd  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x18005c702  lea     rbx, [rax+48h]
0x18005c706  cmp     qword ptr [rbx], 0
0x18005c70a  jnz     short loc_18005C720
0x18005c70c  lea     r8, aStgcreatedocfi; "StgCreateDocfileOnILockBytes"
0x18005c713  mov     edx, 1
0x18005c718  mov     rcx, rbx
0x18005c71b  call    SetProcAddr
0x18005c720  mov     rax, [rbx]
0x18005c723  test    rax, rax
0x18005c726  jz      short loc_18005C740
0x18005c728  lea     r9, [rbp+arg_10]
0x18005c72c  xor     r8d, r8d
0x18005c72f  mov     edx, 11012h
0x18005c734  mov     rcx, rsi
0x18005c737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c73c  mov     ebx, eax
0x18005c73e  jmp     short loc_18005C745
0x18005c740  mov     ebx, 80004005h
0x18005c745  mov     rcx, [rbp+arg_18]
0x18005c749  mov     rax, [rcx]
0x18005c74c  mov     rax, [rax+10h]
0x18005c750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c755  mov     rcx, [rbp+arg_0]; struct IPersistStorage *
0x18005c759  test    ebx, ebx
0x18005c75b  jnz     short loc_18005C7A5
0x18005c75d  mov     rdx, [rbp+arg_10]; struct IStorage *
0x18005c761  xor     r8d, r8d; int
0x18005c764  mov     [rdi+68h], rdx
0x18005c768  call    ?OleSave@CW32System@@SAJPEAUIPersistStorage@@PEAUIStorage@@H@Z; CW32System::OleSave(IPersistStorage *,IStorage *,int)
0x18005c76d  mov     rcx, [rbp+arg_0]
0x18005c771  mov     ebx, eax
0x18005c773  mov     rdx, [rcx]
0x18005c776  mov     rax, [rdx+40h]
0x18005c77a  xor     edx, edx
0x18005c77c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c781  test    ebx, ebx
0x18005c783  jnz     short loc_18005C789
0x18005c785  test    eax, eax
0x18005c787  jz      short loc_18005C791
0x18005c789  mov     [rbp+arg_10], 0
0x18005c791  mov     rcx, [rbp+arg_0]
0x18005c795  mov     rax, [rcx]
0x18005c798  mov     rax, [rax+10h]
0x18005c79c  jmp     loc_18005C674
0x18005c7a1  mov     rcx, [rbp+arg_0]
0x18005c7a5  mov     rax, [rcx]
0x18005c7a8  mov     rax, [rax+10h]
0x18005c7ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c7b1  jmp     loc_18005C698
0x18005c7b6  mov     rdx, [rdi+60h]; struct IOleObject *
0x18005c7ba  xor     r8d, r8d; struct IStorage *
0x18005c7bd  mov     rcx, rdi; this
0x18005c7c0  call    ?GetDataForEmbeddedObject@CDataTransferObj@@AEAAPEAUIStorage@@PEAUIOleObject@@PEAU2@@Z; CDataTransferObj::GetDataForEmbeddedObject(IOleObject *,IStorage *)
0x18005c7c5  mov     rcx, [rbp+arg_0]
0x18005c7c9  mov     [rdi+68h], rax
0x18005c7cd  mov     rax, [rcx]
0x18005c7d0  mov     rax, [rax+10h]
0x18005c7d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c7d9  mov     r8, [rbp+arg_10]; struct IStorage *
0x18005c7dd  mov     rcx, rdi; this
0x18005c7e0  mov     rdx, [rdi+60h]; struct IOleObject *
0x18005c7e4  call    ?GetDataForEmbeddedObject@CDataTransferObj@@AEAAPEAUIStorage@@PEAUIOleObject@@PEAU2@@Z; CDataTransferObj::GetDataForEmbeddedObject(IOleObject *,IStorage *)
0x18005c7e9  mov     rbx, [rsp+30h+arg_8]
0x18005c7ee  add     rsp, 30h
0x18005c7f2  pop     rdi
0x18005c7f3  pop     rsi
0x18005c7f4  pop     rbp
0x18005c7f5  retn
```
