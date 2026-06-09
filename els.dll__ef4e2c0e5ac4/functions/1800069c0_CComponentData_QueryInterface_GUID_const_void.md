# CComponentData::QueryInterface(_GUID const &,void * *)

- ea: `0x1800069c0`
- end: `0x180006b45`
- name: `?QueryInterface@CComponentData@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `389`
- prototype: `__int64 __fastcall(CComponentData *__hidden this, const struct _GUID *, void **)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006b50`
- `0x180006b60`
- `0x180006b70`
- `0x180006b80`
- `0x180006b90`
- `0x180006ba0`

## callees

- `0x1800069c0`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall CComponentData::QueryInterface(CComponentData *this, const struct _GUID *a2, CComponentData **a3)
{
  unsigned int v4; // ebx
  __int64 v5; // rax
  CComponentData *v6; // rax
  __int64 v7; // rax
  unsigned __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax

  if ( a3 )
  {
    v5 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
      v5 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IUnknown.Data4;
    if ( !v5 )
      goto LABEL_6;
    v7 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IComponentData.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IComponentData.Data1 )
      v7 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IComponentData.Data4;
    if ( v7 )
    {
      v9 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IExtendPropertySheet.Data1;
      if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IExtendPropertySheet.Data1 )
        v9 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IExtendPropertySheet.Data4;
      if ( v9 )
      {
        v10 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IExtendContextMenu.Data1;
        if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IExtendContextMenu.Data1 )
          v10 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IExtendContextMenu.Data4;
        if ( v10 )
        {
          v11 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IPersist.Data1;
          if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IPersist.Data1 )
            v11 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IPersist.Data4;
          if ( !v11 )
            goto LABEL_6;
          v12 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IPersistStream.Data1;
          if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IPersistStream.Data1 )
            v12 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IPersistStream.Data4;
          if ( !v12 )
          {
LABEL_6:
            v6 = this;
LABEL_38:
            *a3 = v6;
            v4 = 0;
            (*(void (__fastcall **)(CComponentData *))(*(_QWORD *)this + 8LL))(this);
            return v4;
          }
          v13 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_INamespacePrshtActions.Data1;
          if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_INamespacePrshtActions.Data1 )
            v13 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_INamespacePrshtActions.Data4;
          if ( v13 )
          {
            v14 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IExternalConnection.Data1;
            if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IExternalConnection.Data1 )
              v14 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IExternalConnection.Data4;
            if ( v14 )
            {
              v15 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_ISnapinHelp.Data1;
              if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISnapinHelp.Data1 )
                v15 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_ISnapinHelp.Data4;
              if ( v15 )
              {
                v4 = -2147467262;
                *a3 = 0;
                return v4;
              }
              v8 = (unsigned __int64)this + 48;
            }
            else
            {
              v8 = (unsigned __int64)this + 40;
            }
          }
          else
          {
            v8 = (unsigned __int64)this + 32;
          }
        }
        else
        {
          v8 = (unsigned __int64)this + 24;
        }
      }
      else
      {
        v8 = (unsigned __int64)this + 16;
      }
    }
    else
    {
      v8 = (unsigned __int64)this + 8;
    }
    v6 = (CComponentData *)(v8 & -(__int64)(this != 0));
    goto LABEL_38;
  }
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x1800069c0  push    rbx
0x1800069c2  sub     rsp, 20h
0x1800069c6  mov     r9, rcx
0x1800069c9  test    r8, r8
0x1800069cc  jnz     short loc_1800069D8
0x1800069ce  mov     ebx, 80070057h
0x1800069d3  jmp     loc_180006B3D
0x1800069d8  mov     rax, [rdx]
0x1800069db  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x1800069e2  jnz     short loc_1800069EF
0x1800069e4  mov     rax, [rdx+8]
0x1800069e8  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x1800069ef  test    rax, rax
0x1800069f2  jnz     short loc_1800069FC
0x1800069f4  mov     rax, r9
0x1800069f7  jmp     loc_180006B1B
0x1800069fc  mov     rax, [rdx]
0x1800069ff  sub     rax, qword ptr cs:IID_IComponentData.Data1
0x180006a06  jnz     short loc_180006A13
0x180006a08  mov     rax, [rdx+8]
0x180006a0c  sub     rax, qword ptr cs:IID_IComponentData.Data4
0x180006a13  test    rax, rax
0x180006a16  jnz     short loc_180006A21
0x180006a18  add     rcx, 8
0x180006a1c  jmp     loc_180006B0F
0x180006a21  mov     rax, [rdx]
0x180006a24  sub     rax, qword ptr cs:IID_IExtendPropertySheet.Data1
0x180006a2b  jnz     short loc_180006A38
0x180006a2d  mov     rax, [rdx+8]
0x180006a31  sub     rax, qword ptr cs:IID_IExtendPropertySheet.Data4
0x180006a38  test    rax, rax
0x180006a3b  jnz     short loc_180006A46
0x180006a3d  add     rcx, 10h
0x180006a41  jmp     loc_180006B0F
0x180006a46  mov     rax, [rdx]
0x180006a49  sub     rax, qword ptr cs:IID_IExtendContextMenu.Data1
0x180006a50  jnz     short loc_180006A5D
0x180006a52  mov     rax, [rdx+8]
0x180006a56  sub     rax, qword ptr cs:IID_IExtendContextMenu.Data4
0x180006a5d  test    rax, rax
0x180006a60  jnz     short loc_180006A6B
0x180006a62  add     rcx, 18h
0x180006a66  jmp     loc_180006B0F
0x180006a6b  mov     rax, [rdx]
0x180006a6e  sub     rax, qword ptr cs:IID_IPersist.Data1
0x180006a75  jnz     short loc_180006A82
0x180006a77  mov     rax, [rdx+8]
0x180006a7b  sub     rax, qword ptr cs:IID_IPersist.Data4
0x180006a82  test    rax, rax
0x180006a85  jz      loc_1800069F4
0x180006a8b  mov     rax, [rdx]
0x180006a8e  sub     rax, qword ptr cs:IID_IPersistStream.Data1
0x180006a95  jnz     short loc_180006AA2
0x180006a97  mov     rax, [rdx+8]
0x180006a9b  sub     rax, qword ptr cs:IID_IPersistStream.Data4
0x180006aa2  test    rax, rax
0x180006aa5  jz      loc_1800069F4
0x180006aab  mov     rax, [rdx]
0x180006aae  sub     rax, qword ptr cs:IID_INamespacePrshtActions.Data1
0x180006ab5  jnz     short loc_180006AC2
0x180006ab7  mov     rax, [rdx+8]
0x180006abb  sub     rax, qword ptr cs:IID_INamespacePrshtActions.Data4
0x180006ac2  test    rax, rax
0x180006ac5  jnz     short loc_180006ACD
0x180006ac7  add     rcx, 20h ; ' '
0x180006acb  jmp     short loc_180006B0F
0x180006acd  mov     rax, [rdx]
0x180006ad0  sub     rax, qword ptr cs:IID_IExternalConnection.Data1
0x180006ad7  jnz     short loc_180006AE4
0x180006ad9  mov     rax, [rdx+8]
0x180006add  sub     rax, qword ptr cs:IID_IExternalConnection.Data4
0x180006ae4  test    rax, rax
0x180006ae7  jnz     short loc_180006AEF
0x180006ae9  add     rcx, 28h ; '('
0x180006aed  jmp     short loc_180006B0F
0x180006aef  mov     rax, [rdx]
0x180006af2  sub     rax, qword ptr cs:IID_ISnapinHelp.Data1
0x180006af9  jnz     short loc_180006B06
0x180006afb  mov     rax, [rdx+8]
0x180006aff  sub     rax, qword ptr cs:IID_ISnapinHelp.Data4
0x180006b06  test    rax, rax
0x180006b09  jnz     short loc_180006B31
0x180006b0b  add     rcx, 30h ; '0'
0x180006b0f  mov     rax, r9
0x180006b12  neg     rax
0x180006b15  sbb     rax, rax
0x180006b18  and     rax, rcx
0x180006b1b  mov     [r8], rax
0x180006b1e  xor     ebx, ebx
0x180006b20  mov     rax, [r9]
0x180006b23  mov     rcx, r9
0x180006b26  mov     rax, [rax+8]
0x180006b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b2f  jmp     short loc_180006B3D
0x180006b31  mov     ebx, 80004002h
0x180006b36  mov     qword ptr [r8], 0
0x180006b3d  mov     eax, ebx
0x180006b3f  add     rsp, 20h
0x180006b43  pop     rbx
0x180006b44  retn
```
