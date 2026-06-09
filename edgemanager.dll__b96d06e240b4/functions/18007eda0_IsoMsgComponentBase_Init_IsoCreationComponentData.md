# IsoMsgComponentBase::Init(_IsoCreationComponentData *)

- ea: `0x18007eda0`
- end: `0x18007eea8`
- name: `?Init@IsoMsgComponentBase@@MEAAJPEAU_IsoCreationComponentData@@@Z`
- size: `264`
- prototype: `__int64 __fastcall(IsoMsgComponentBase *__hidden this, struct _IsoCreationComponentData *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180022e9c`

## callees

- `0x18006ea64`
- `0x18007eda0`
- `0x180085010`

## import_xrefs

- `edgeIso!__imp_?IsoGetArtifactAddress@@YAJKW4IsoArtifactType@@PEAPEAU_IsoArtifact@@PEAK@Z` at `0x18007edcd`
- `edgeIso!__imp_?IsoGetArtifactAddress@@YAJKW4IsoArtifactType@@PEAPEAU_IsoArtifact@@PEAK@Z` at `0x18007edcd`
- `edgeIso!__imp_?IsoLockArtifact@@YAJKW4IsoArtifactType@@PEAPEAU_IsoArtifact@@PEAK@Z` at `0x18007ee65`
- `edgeIso!__imp_?IsoLockArtifact@@YAJKW4IsoArtifactType@@PEAPEAU_IsoArtifact@@PEAK@Z` at `0x18007ee65`
- `edgeIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x18007ee7e`
- `edgeIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x18007ee7e`
- `edgeIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x18007ee93`
- `edgeIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x18007ee93`
- `edgeIso!__imp_?IsoGetCurrentThreadHandle@@YAKXZ` at `0x18007ee4f`
- `edgeIso!__imp_?IsoGetCurrentThreadHandle@@YAKXZ` at `0x18007ee4f`
- `edgeIso!__imp_?IsoReferenceThread@@YAKK@Z` at `0x18007ede5`
- `edgeIso!__imp_?IsoReferenceThread@@YAKK@Z` at `0x18007ede5`
- `edgeIso!__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z` at `0x18007ee40`
- `edgeIso!__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z` at `0x18007ee40`

## pseudocode

```c
__int64 __fastcall IsoMsgComponentBase::Init(IsoMsgComponentBase *this, struct _IsoCreationComponentData *a2)
{
  int ArtifactAddress; // ebx
  _IsoComponent *v5; // rcx
  __int64 CurrentThreadHandle; // rbp
  _IsoComponent *v8; // [rsp+48h] [rbp+10h] BYREF
  __int64 v9; // [rsp+50h] [rbp+18h] BYREF
  __int64 (__fastcall *v10)(unsigned int, struct tagMSG *); // [rsp+58h] [rbp+20h] BYREF

  v8 = 0;
  ArtifactAddress = IsoGetArtifactAddress(*((unsigned int *)a2 + 102), 1, &v8);
  if ( ArtifactAddress < 0 )
    goto LABEL_6;
  ArtifactAddress = IsoReferenceThread(*((_DWORD *)v8 + 10));
  if ( ArtifactAddress < 0 )
    goto LABEL_6;
  v5 = v8;
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 102);
  _IsoComponent::SetAppObj(v5, this);
  if ( (*(unsigned __int8 (__fastcall **)(IsoMsgComponentBase *))(*(_QWORD *)this + 48LL))(this) )
  {
    v10 = IsoMsgComponentBase::s_IsoMsgComponentBaseTryTranslateAccelerator;
    IsoInProcessData(v8, 0x10040001u, *((_DWORD *)v8 + 65), &v10);
    v9 = 0;
    CurrentThreadHandle = IsoGetCurrentThreadHandle();
    ArtifactAddress = IsoLockArtifact(CurrentThreadHandle, 3, &v9);
    if ( ArtifactAddress >= 0 )
    {
      *(_DWORD *)(v9 + 48) = *((_DWORD *)this + 2);
      IsoUnlockArtifact(CurrentThreadHandle);
      return (unsigned int)ArtifactAddress;
    }
LABEL_6:
    *((_DWORD *)this + 2) = 0;
    IsoRemoveArtifact(*((_DWORD *)a2 + 102));
  }
  return (unsigned int)ArtifactAddress;
}

```

## disassembly

```asm
0x18007eda0  mov     [rsp+arg_0], rbx
0x18007eda5  push    rbp
0x18007eda6  push    rsi
0x18007eda7  push    rdi
0x18007eda8  sub     rsp, 20h
0x18007edac  mov     rsi, rdx
0x18007edaf  mov     [rsp+38h+arg_8], 0
0x18007edb8  xor     r9d, r9d
0x18007edbb  lea     r8, [rsp+38h+arg_8]
0x18007edc0  mov     rdi, rcx
0x18007edc3  mov     ecx, [rsi+198h]
0x18007edc9  lea     edx, [r9+1]
0x18007edcd  call    cs:__imp_?IsoGetArtifactAddress@@YAJKW4IsoArtifactType@@PEAPEAU_IsoArtifact@@PEAK@Z; IsoGetArtifactAddress(ulong,IsoArtifactType,_IsoArtifact * *,ulong *)
0x18007edd3  mov     ebx, eax
0x18007edd5  test    eax, eax
0x18007edd7  js      loc_18007EE86
0x18007eddd  mov     rcx, [rsp+38h+arg_8]
0x18007ede2  mov     ecx, [rcx+28h]
0x18007ede5  call    cs:__imp_?IsoReferenceThread@@YAKK@Z; IsoReferenceThread(ulong)
0x18007edeb  mov     ebx, eax
0x18007eded  test    eax, eax
0x18007edef  js      loc_18007EE86
0x18007edf5  mov     eax, [rsi+198h]
0x18007edfb  mov     rdx, rdi; void *
0x18007edfe  mov     rcx, [rsp+38h+arg_8]; this
0x18007ee03  mov     [rdi+8], eax
0x18007ee06  call    ?SetAppObj@_IsoComponent@@QEAAXQEAX@Z; _IsoComponent::SetAppObj(void * const)
0x18007ee0b  mov     rax, [rdi]
0x18007ee0e  mov     rcx, rdi
0x18007ee11  mov     rax, [rax+30h]
0x18007ee15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ee1a  test    al, al
0x18007ee1c  jz      short loc_18007EE99
0x18007ee1e  mov     rcx, [rsp+38h+arg_8]
0x18007ee23  lea     rax, ?s_IsoMsgComponentBaseTryTranslateAccelerator@IsoMsgComponentBase@@KAJKPEAUtagMSG@@@Z; IsoMsgComponentBase::s_IsoMsgComponentBaseTryTranslateAccelerator(ulong,tagMSG *)
0x18007ee2a  mov     [rsp+38h+arg_18], rax
0x18007ee2f  lea     r9, [rsp+38h+arg_18]
0x18007ee34  mov     edx, 10040001h
0x18007ee39  mov     r8d, [rcx+104h]
0x18007ee40  call    cs:__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z; IsoInProcessData(_IsoArtifact *,ulong,ulong,void *)
0x18007ee46  mov     [rsp+38h+arg_10], 0
0x18007ee4f  call    cs:__imp_?IsoGetCurrentThreadHandle@@YAKXZ; IsoGetCurrentThreadHandle(void)
0x18007ee55  xor     r9d, r9d
0x18007ee58  lea     r8, [rsp+38h+arg_10]
0x18007ee5d  mov     ecx, eax
0x18007ee5f  mov     ebp, eax
0x18007ee61  lea     edx, [r9+3]
0x18007ee65  call    cs:__imp_?IsoLockArtifact@@YAJKW4IsoArtifactType@@PEAPEAU_IsoArtifact@@PEAK@Z; IsoLockArtifact(ulong,IsoArtifactType,_IsoArtifact * *,ulong *)
0x18007ee6b  mov     ebx, eax
0x18007ee6d  test    eax, eax
0x18007ee6f  js      short loc_18007EE86
0x18007ee71  mov     rcx, [rsp+38h+arg_10]
0x18007ee76  mov     edx, [rdi+8]
0x18007ee79  mov     [rcx+30h], edx
0x18007ee7c  mov     ecx, ebp
0x18007ee7e  call    cs:__imp_?IsoUnlockArtifact@@YAJK@Z; IsoUnlockArtifact(ulong)
0x18007ee84  jmp     short loc_18007EE99
0x18007ee86  mov     dword ptr [rdi+8], 0
0x18007ee8d  mov     ecx, [rsi+198h]
0x18007ee93  call    cs:__imp_?IsoRemoveArtifact@@YAJK@Z; IsoRemoveArtifact(ulong)
0x18007ee99  mov     eax, ebx
0x18007ee9b  mov     rbx, [rsp+38h+arg_0]
0x18007eea0  add     rsp, 20h
0x18007eea4  pop     rdi
0x18007eea5  pop     rsi
0x18007eea6  pop     rbp
0x18007eea7  retn
```
