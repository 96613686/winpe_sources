# CDataTransferObj::GetDataForEmbeddedObject(IOleObject *,IStorage *)

- ea: `0x18005afc8`
- end: `0x18005b1b6`
- name: `?GetDataForEmbeddedObject@CDataTransferObj@@AEAAPEAUIStorage@@PEAUIOleObject@@PEAU2@@Z`
- size: `494`
- prototype: `struct IStorage *__fastcall(CDataTransferObj *__hidden this, struct IOleObject *, struct IStorage *)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18005a618`
- `0x18005ad00`
- `0x18005afc8`
- `0x18005b1c0`

## callees

- `0x180041adc`
- `0x18005afc8`
- `0x18008ff64`
- `0x1800907ac`
- `0x180092010`

## string_xrefs

- `0x18005b0cc`: `StgCreateDocfileOnILockBytes`
- `0x18005b081`: `CreateILockBytesOnHGlobal`

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
      SetProcAddr((char *)Ole32Procs + 80, 1, "CreateILockBytesOnHGlobal");
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
        SetProcAddr((char *)v10 + 72, 1, "StgCreateDocfileOnILockBytes");
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
0x18005afc8  mov     [rsp-18h+arg_8], rbx
0x18005afcd  mov     [rsp-18h+arg_10], r8
0x18005afd2  push    rbp
0x18005afd3  push    rsi
0x18005afd4  push    rdi
0x18005afd5  mov     rbp, rsp
0x18005afd8  sub     rsp, 30h
0x18005afdc  mov     rdi, rcx
0x18005afdf  mov     [rbp+arg_0], 0
0x18005afe7  mov     rcx, [rcx+68h]
0x18005afeb  mov     r9, rdx
0x18005afee  test    rcx, rcx
0x18005aff1  jz      short loc_18005B03B
0x18005aff3  mov     rax, [rcx]
0x18005aff6  test    r8, r8
0x18005aff9  jz      short loc_18005B030
0x18005affb  mov     rax, [rax+38h]
0x18005afff  xor     r9d, r9d
0x18005b002  mov     [rsp+30h+var_10], r8
0x18005b007  xor     edx, edx
0x18005b009  xor     r8d, r8d
0x18005b00c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b011  test    eax, eax
0x18005b013  jnz     short loc_18005B058
0x18005b015  mov     rcx, [rbp+arg_10]
0x18005b019  xor     edx, edx
0x18005b01b  mov     rax, [rcx]
0x18005b01e  mov     rax, [rax+48h]
0x18005b022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b027  mov     rax, [rdi+68h]
0x18005b02b  jmp     loc_18005B1A9
0x18005b030  mov     rax, [rax+8]
0x18005b034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b039  jmp     short loc_18005B027
0x18005b03b  mov     rax, [rdx]
0x18005b03e  lea     r8, [rbp+arg_0]
0x18005b042  lea     rdx, IID_IPersistStorage
0x18005b049  mov     rcx, r9
0x18005b04c  mov     rax, [rax]
0x18005b04f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b054  test    eax, eax
0x18005b056  jz      short loc_18005B05F
0x18005b058  xor     eax, eax
0x18005b05a  jmp     loc_18005B1A9
0x18005b05f  cmp     [rbp+arg_10], 0
0x18005b064  jnz     loc_18005B176
0x18005b06a  mov     [rbp+arg_18], 0
0x18005b072  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x18005b077  lea     rbx, [rax+50h]
0x18005b07b  cmp     qword ptr [rbx], 0
0x18005b07f  jnz     short loc_18005B095
0x18005b081  lea     r8, aCreateilockbyt; "CreateILockBytesOnHGlobal"
0x18005b088  mov     edx, 1
0x18005b08d  mov     rcx, rbx
0x18005b090  call    SetProcAddr
0x18005b095  mov     rax, [rbx]
0x18005b098  test    rax, rax
0x18005b09b  jz      loc_18005B161
0x18005b0a1  lea     r8, [rbp+arg_18]
0x18005b0a5  mov     edx, 1
0x18005b0aa  xor     ecx, ecx
0x18005b0ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b0b1  test    eax, eax
0x18005b0b3  jnz     loc_18005B161
0x18005b0b9  mov     rsi, [rbp+arg_18]
0x18005b0bd  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x18005b0c2  lea     rbx, [rax+48h]
0x18005b0c6  cmp     qword ptr [rbx], 0
0x18005b0ca  jnz     short loc_18005B0E0
0x18005b0cc  lea     r8, aStgcreatedocfi; "StgCreateDocfileOnILockBytes"
0x18005b0d3  mov     edx, 1
0x18005b0d8  mov     rcx, rbx
0x18005b0db  call    SetProcAddr
0x18005b0e0  mov     rax, [rbx]
0x18005b0e3  test    rax, rax
0x18005b0e6  jz      short loc_18005B100
0x18005b0e8  lea     r9, [rbp+arg_10]
0x18005b0ec  xor     r8d, r8d
0x18005b0ef  mov     edx, 11012h
0x18005b0f4  mov     rcx, rsi
0x18005b0f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b0fc  mov     ebx, eax
0x18005b0fe  jmp     short loc_18005B105
0x18005b100  mov     ebx, 80004005h
0x18005b105  mov     rcx, [rbp+arg_18]
0x18005b109  mov     rax, [rcx]
0x18005b10c  mov     rax, [rax+10h]
0x18005b110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b115  mov     rcx, [rbp+arg_0]; struct IPersistStorage *
0x18005b119  test    ebx, ebx
0x18005b11b  jnz     short loc_18005B165
0x18005b11d  mov     rdx, [rbp+arg_10]; struct IStorage *
0x18005b121  xor     r8d, r8d; int
0x18005b124  mov     [rdi+68h], rdx
0x18005b128  call    ?OleSave@CW32System@@SAJPEAUIPersistStorage@@PEAUIStorage@@H@Z; CW32System::OleSave(IPersistStorage *,IStorage *,int)
0x18005b12d  mov     rcx, [rbp+arg_0]
0x18005b131  mov     ebx, eax
0x18005b133  mov     rdx, [rcx]
0x18005b136  mov     rax, [rdx+40h]
0x18005b13a  xor     edx, edx
0x18005b13c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b141  test    ebx, ebx
0x18005b143  jnz     short loc_18005B149
0x18005b145  test    eax, eax
0x18005b147  jz      short loc_18005B151
0x18005b149  mov     [rbp+arg_10], 0
0x18005b151  mov     rcx, [rbp+arg_0]
0x18005b155  mov     rax, [rcx]
0x18005b158  mov     rax, [rax+10h]
0x18005b15c  jmp     loc_18005B034
0x18005b161  mov     rcx, [rbp+arg_0]
0x18005b165  mov     rax, [rcx]
0x18005b168  mov     rax, [rax+10h]
0x18005b16c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b171  jmp     loc_18005B058
0x18005b176  mov     rdx, [rdi+60h]; struct IOleObject *
0x18005b17a  xor     r8d, r8d; struct IStorage *
0x18005b17d  mov     rcx, rdi; this
0x18005b180  call    ?GetDataForEmbeddedObject@CDataTransferObj@@AEAAPEAUIStorage@@PEAUIOleObject@@PEAU2@@Z; CDataTransferObj::GetDataForEmbeddedObject(IOleObject *,IStorage *)
0x18005b185  mov     rcx, [rbp+arg_0]
0x18005b189  mov     [rdi+68h], rax
0x18005b18d  mov     rax, [rcx]
0x18005b190  mov     rax, [rax+10h]
0x18005b194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b199  mov     r8, [rbp+arg_10]; struct IStorage *
0x18005b19d  mov     rcx, rdi; this
0x18005b1a0  mov     rdx, [rdi+60h]; struct IOleObject *
0x18005b1a4  call    ?GetDataForEmbeddedObject@CDataTransferObj@@AEAAPEAUIStorage@@PEAUIOleObject@@PEAU2@@Z; CDataTransferObj::GetDataForEmbeddedObject(IOleObject *,IStorage *)
0x18005b1a9  mov     rbx, [rsp+30h+arg_8]
0x18005b1ae  add     rsp, 30h
0x18005b1b2  pop     rdi
0x18005b1b3  pop     rsi
0x18005b1b4  pop     rbp
0x18005b1b5  retn
```
