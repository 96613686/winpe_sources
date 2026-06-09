# CDelayedPropertyStore_CreateInstance

- ea: `0x18001dae0`
- end: `0x18001dc1b`
- name: `CDelayedPropertyStore_CreateInstance`
- size: `315`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18001dae0`
- `0x18001dc24`
- `0x18001dcc0`
- `0x18001dd30`
- `0x18001e2e0`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dafe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dafe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001db12`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001db12`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18001db7c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18001db98`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18001db7c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18001db98`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18001dc05`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18001dc05`

## pseudocode

```c
__int64 __fastcall CDelayedPropertyStore_CreateInstance(__int64 a1, __int64 a2, const IID *a3, void **a4)
{
  HRESULT ApartmentId; // ebx
  HANDLE ProcessHeap; // rax
  CDelayedPropertyStore *v8; // rax
  CDelayedPropertyStore *v9; // rax
  CDelayedPropertyStore *v10; // rdi
  __int64 v11; // rax
  __int64 v13; // rax
  _QWORD *v14; // r14

  *a4 = 0;
  ApartmentId = -2147024882;
  ProcessHeap = GetProcessHeap();
  v8 = (CDelayedPropertyStore *)HeapAlloc(ProcessHeap, 8u, 0xC0u);
  if ( v8 )
  {
    v9 = CDelayedPropertyStore::CDelayedPropertyStore(v8);
    v10 = v9;
    if ( v9 )
    {
      if ( !(unsigned __int8)_ShouldCheckApartments(*((unsigned int *)v9 + 27))
        || (ApartmentId = SHCoGetApartmentId((unsigned int *)v10 + 26), ApartmentId >= 0) )
      {
        v11 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IInitializeWithPropertyStores.Data1;
        if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IInitializeWithPropertyStores.Data1 )
          v11 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IInitializeWithPropertyStores.Data4;
        if ( v11 )
        {
          ApartmentId = QISearch(v10, &stru_1800B1850, a3, a4);
          if ( ApartmentId < 0 )
          {
            ApartmentId = QISearch(v10, &stru_1800B0FE0, a3, a4);
            if ( ApartmentId < 0 )
            {
              v13 = *(_QWORD *)&IID_IMarshal.Data1 - *(_QWORD *)&a3->Data1;
              if ( *(_QWORD *)&IID_IMarshal.Data1 == *(_QWORD *)&a3->Data1 )
                v13 = *(_QWORD *)IID_IMarshal.Data4 - *(_QWORD *)a3->Data4;
              if ( !v13 )
              {
                v14 = (_QWORD *)((char *)v10 + 144);
                if ( !*((_QWORD *)v10 + 18) )
                  CoCreateFreeThreadedMarshaler((LPUNKNOWN)v10, (LPUNKNOWN *)v10 + 18);
                if ( *v14 )
                  ApartmentId = (**(__int64 (__fastcall ***)(_QWORD, const IID *, void **))*v14)(*v14, a3, a4);
              }
            }
          }
        }
        else
        {
          *a4 = 0;
          ApartmentId = -2147467262;
        }
      }
      CMultiplexPropertyStore::Release(v10);
    }
  }
  return (unsigned int)ApartmentId;
}

```

## disassembly

```asm
0x18001dae0  push    rbx
0x18001dae2  push    rsi
0x18001dae3  push    rdi
0x18001dae4  push    r14
0x18001dae6  push    r15
0x18001dae8  sub     rsp, 20h
0x18001daec  mov     r15, r9
0x18001daef  mov     qword ptr [r9], 0
0x18001daf6  mov     rsi, r8
0x18001daf9  mov     ebx, 8007000Eh
0x18001dafe  call    cs:__imp_GetProcessHeap
0x18001db04  mov     edx, 8; dwFlags
0x18001db09  mov     r8d, 0C0h; dwBytes
0x18001db0f  mov     rcx, rax; hHeap
0x18001db12  call    cs:__imp_HeapAlloc
0x18001db18  test    rax, rax
0x18001db1b  jz      loc_18001DBAC
0x18001db21  mov     rcx, rax; this
0x18001db24  call    ??0CDelayedPropertyStore@@QEAA@XZ; CDelayedPropertyStore::CDelayedPropertyStore(void)
0x18001db29  mov     rdi, rax
0x18001db2c  test    rax, rax
0x18001db2f  jz      short loc_18001DBAC
0x18001db31  mov     ecx, [rax+6Ch]
0x18001db34  call    ?_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z; _ShouldCheckApartments(ApartmentCheckEnum)
0x18001db39  test    al, al
0x18001db3b  jz      short loc_18001DB4C
0x18001db3d  lea     rcx, [rdi+68h]; unsigned int *
0x18001db41  call    ?SHCoGetApartmentId@@YAJPEAK@Z; SHCoGetApartmentId(ulong *)
0x18001db46  mov     ebx, eax
0x18001db48  test    eax, eax
0x18001db4a  js      short loc_18001DBA4
0x18001db4c  mov     rax, [rsi]
0x18001db4f  sub     rax, qword ptr cs:IID_IInitializeWithPropertyStores.Data1
0x18001db56  jnz     short loc_18001DB63
0x18001db58  mov     rax, [rsi+8]
0x18001db5c  sub     rax, qword ptr cs:IID_IInitializeWithPropertyStores.Data4
0x18001db63  test    rax, rax
0x18001db66  jz      loc_18001DC0D
0x18001db6c  mov     r9, r15; ppv
0x18001db6f  lea     rdx, stru_1800B1850; pqit
0x18001db76  mov     r8, rsi; riid
0x18001db79  mov     rcx, rdi; that
0x18001db7c  call    cs:__imp_QISearch
0x18001db82  mov     ebx, eax
0x18001db84  test    eax, eax
0x18001db86  jns     short loc_18001DBA4
0x18001db88  mov     r9, r15; ppv
0x18001db8b  lea     rdx, stru_1800B0FE0; pqit
0x18001db92  mov     r8, rsi; riid
0x18001db95  mov     rcx, rdi; that
0x18001db98  call    cs:__imp_QISearch
0x18001db9e  mov     ebx, eax
0x18001dba0  test    eax, eax
0x18001dba2  js      short loc_18001DBBA
0x18001dba4  mov     rcx, rdi; this
0x18001dba7  call    ?Release@CMultiplexPropertyStore@@UEAAKXZ; CMultiplexPropertyStore::Release(void)
0x18001dbac  mov     eax, ebx
0x18001dbae  add     rsp, 20h
0x18001dbb2  pop     r15
0x18001dbb4  pop     r14
0x18001dbb6  pop     rdi
0x18001dbb7  pop     rsi
0x18001dbb8  pop     rbx
0x18001dbb9  retn
0x18001dbba  mov     rax, qword ptr cs:IID_IMarshal.Data1
0x18001dbc1  sub     rax, [rsi]
0x18001dbc4  jnz     short loc_18001DBD1
0x18001dbc6  mov     rax, qword ptr cs:IID_IMarshal.Data4
0x18001dbcd  sub     rax, [rsi+8]
0x18001dbd1  test    rax, rax
0x18001dbd4  jnz     short loc_18001DBA4
0x18001dbd6  lea     r14, [rdi+90h]
0x18001dbdd  cmp     [r14], rax
0x18001dbe0  jz      short loc_18001DBFF
0x18001dbe2  mov     rcx, [r14]
0x18001dbe5  test    rcx, rcx
0x18001dbe8  jz      short loc_18001DBA4
0x18001dbea  mov     rax, [rcx]
0x18001dbed  mov     r8, r15
0x18001dbf0  mov     rdx, rsi
0x18001dbf3  mov     rax, [rax]
0x18001dbf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbfb  mov     ebx, eax
0x18001dbfd  jmp     short loc_18001DBA4
0x18001dbff  mov     rdx, r14; ppunkMarshal
0x18001dc02  mov     rcx, rdi; punkOuter
0x18001dc05  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18001dc0b  jmp     short loc_18001DBE2
0x18001dc0d  mov     qword ptr [r15], 0
0x18001dc14  mov     ebx, 80004002h
0x18001dc19  jmp     short loc_18001DBA4
```
