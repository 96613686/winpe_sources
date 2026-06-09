# IsoMsgComponentBase::s_IsoMsgDispatcher(uint,unsigned __int64,__int64)

- ea: `0x18007ef3c`
- end: `0x18007f0fb`
- name: `?s_IsoMsgDispatcher@IsoMsgComponentBase@@CAJI_K_J@Z`
- size: `447`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18007ef20`

## callees

- `0x180035b88`
- `0x180035ba8`
- `0x18006ea64`
- `0x18007ef3c`
- `0x180085010`

## import_xrefs

- `edgeIso!__imp_?IsoGetArtifactAddress@@YAJKW4IsoArtifactType@@PEAPEAU_IsoArtifact@@PEAK@Z` at `0x18007efb4`
- `edgeIso!__imp_?IsoGetArtifactAddress@@YAJKW4IsoArtifactType@@PEAPEAU_IsoArtifact@@PEAK@Z` at `0x18007efb4`
- `edgeIso!__imp_?IsoReleaseThread@@YAKK@Z` at `0x18007f0bd`
- `edgeIso!__imp_?IsoReleaseThread@@YAKK@Z` at `0x18007f0bd`
- `edgeIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x18007f011`
- `edgeIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x18007f011`
- `edgeIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x18007ef78`
- `edgeIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x18007ef78`
- `edgeIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x18007f0e8`
- `edgeIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x18007f0e8`
- `edgeIso!__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z` at `0x18007efea`
- `edgeIso!__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z` at `0x18007efea`

## string_xrefs

- `0x18007ef86`: `onecoreuap\inetcore\edgeisolation\msgcomp\isomsgcomponentbase.cpp`
- `0x18007efc2`: `onecoreuap\inetcore\edgeisolation\msgcomp\isomsgcomponentbase.cpp`
- `0x18007effc`: `onecoreuap\inetcore\edgeisolation\msgcomp\isomsgcomponentbase.cpp`

## pseudocode

```c
__int64 __fastcall IsoMsgComponentBase::s_IsoMsgDispatcher(int a1, __int64 a2, unsigned int a3)
{
  int MessageBufferAddress; // eax
  int ArtifactAddress; // eax
  __int64 *v7; // rbx
  const char *v8; // r9
  int WindowsMessageNumber; // eax
  __int64 v10; // rdx
  bool v11; // r14
  int v12; // edi
  __int64 v13; // rax
  __int64 v14; // rdx
  int v16; // [rsp+20h] [rbp-20h]
  _IsoComponent *v17; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  __int64 v19; // [rsp+78h] [rbp+38h] BYREF
  int v20; // [rsp+80h] [rbp+40h] BYREF
  struct _IsoMessage *v21; // [rsp+88h] [rbp+48h] BYREF

  v19 = a2;
  v21 = 0;
  v20 = 0;
  MessageBufferAddress = IsoGetMessageBufferAddress(a3, 1, 0, &v21, (unsigned int *)&v20);
  if ( MessageBufferAddress < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecoreuap\\inetcore\\edgeisolation\\msgcomp\\isomsgcomponentbase.cpp",
      (const char *)(unsigned int)MessageBufferAddress,
      v16);
  v17 = 0;
  ArtifactAddress = IsoGetArtifactAddress(*(unsigned int *)v21, 1, &v17);
  if ( ArtifactAddress < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"onecoreuap\\inetcore\\edgeisolation\\msgcomp\\isomsgcomponentbase.cpp",
      (const char *)(unsigned int)ArtifactAddress,
      v16);
  v7 = (__int64 *)IsoInProcessData(v17, 0x30001u, *((_DWORD *)v17 + 65), 0);
  if ( !v7 )
    wil::details::in1diag3::_FailFast_NullAlloc(
      retaddr,
      (void *)0x57,
      (unsigned int)"onecoreuap\\inetcore\\edgeisolation\\msgcomp\\isomsgcomponentbase.cpp",
      v8);
  WindowsMessageNumber = IsoGetWindowsMessageNumber(2);
  v11 = a1 == WindowsMessageNumber;
  if ( *((_DWORD *)v21 + 3) == 1159 && a1 == WindowsMessageNumber )
  {
    v12 = (*(__int64 (__fastcall **)(__int64 *))(*v7 + 56))(v7);
  }
  else
  {
    LOBYTE(v10) = a1 == WindowsMessageNumber;
    v12 = 1;
    if ( (*(unsigned __int8 (__fastcall **)(__int64 *, __int64, _QWORD))*v7)(v7, v10, *((unsigned int *)v21 + 1)) )
    {
      v13 = *v7;
      LOBYTE(v19) = 0;
      v12 = (*(__int64 (__fastcall **)(__int64 *, struct _IsoMessage *, __int64 *))(v13 + 24))(v7, v21, &v19);
      if ( v12 >= 0 && !(_BYTE)v19 )
      {
        LOBYTE(v14) = v11;
        v12 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD, struct _IsoMessage *, int))(*v7 + 16))(
                v7,
                v14,
                a3,
                v21,
                v20);
      }
      if ( v12 || (_BYTE)v19 )
      {
        IsoReleaseThread(*((_DWORD *)v17 + 10));
        _IsoComponent::SetAppObj(v17, 0);
        (*(void (__fastcall **)(__int64 *, __int64))(*v7 + 8))(v7, 1);
      }
    }
  }
  if ( a3 )
    IsoFreeMessageBuffer(a3);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18007ef3c  mov     [rsp-28h+arg_8], rdx
0x18007ef41  push    rbp
0x18007ef42  push    rbx
0x18007ef43  push    rsi
0x18007ef44  push    rdi
0x18007ef45  push    r14
0x18007ef47  mov     rbp, rsp
0x18007ef4a  sub     rsp, 40h
0x18007ef4e  mov     rsi, r8
0x18007ef51  mov     [rbp+arg_18], 0
0x18007ef59  xor     r8d, r8d
0x18007ef5c  mov     [rbp+arg_10], 0
0x18007ef63  mov     edi, ecx
0x18007ef65  lea     rax, [rbp+arg_10]
0x18007ef69  lea     r9, [rbp+arg_18]
0x18007ef6d  mov     qword ptr [rsp+40h+var_20], rax; int
0x18007ef72  mov     ecx, esi
0x18007ef74  lea     edx, [r8+1]
0x18007ef78  call    cs:__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z; IsoGetMessageBufferAddress(ulong,int,ulong *,_IsoMessage * *,ulong *)
0x18007ef7e  test    eax, eax
0x18007ef80  jns     short loc_18007EF9B
0x18007ef82  mov     rcx, [rbp+28h]; this
0x18007ef86  lea     r8, aOnecoreuapInet_31; "onecoreuap\\inetcore\\edgeisolation\\ms"...
0x18007ef8d  mov     r9d, eax; char *
0x18007ef90  mov     edx, 51h ; 'Q'; void *
0x18007ef95  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18007ef9b  mov     rcx, [rbp+arg_18]
0x18007ef9f  lea     r8, [rbp+var_10]
0x18007efa3  xor     r9d, r9d
0x18007efa6  mov     [rbp+var_10], 0
0x18007efae  mov     ecx, [rcx]
0x18007efb0  lea     edx, [r9+1]
0x18007efb4  call    cs:__imp_?IsoGetArtifactAddress@@YAJKW4IsoArtifactType@@PEAPEAU_IsoArtifact@@PEAK@Z; IsoGetArtifactAddress(ulong,IsoArtifactType,_IsoArtifact * *,ulong *)
0x18007efba  test    eax, eax
0x18007efbc  jns     short loc_18007EFD7
0x18007efbe  mov     rcx, [rbp+28h]; this
0x18007efc2  lea     r8, aOnecoreuapInet_31; "onecoreuap\\inetcore\\edgeisolation\\ms"...
0x18007efc9  mov     r9d, eax; char *
0x18007efcc  mov     edx, 54h ; 'T'; void *
0x18007efd1  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18007efd7  mov     rcx, [rbp+var_10]
0x18007efdb  xor     r9d, r9d
0x18007efde  mov     edx, 30001h
0x18007efe3  mov     r8d, [rcx+104h]
0x18007efea  call    cs:__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z; IsoInProcessData(_IsoArtifact *,ulong,ulong,void *)
0x18007eff0  mov     rbx, rax
0x18007eff3  test    rax, rax
0x18007eff6  jnz     short loc_18007F00C
0x18007eff8  mov     rcx, [rbp+28h]; this
0x18007effc  lea     r8, aOnecoreuapInet_31; "onecoreuap\\inetcore\\edgeisolation\\ms"...
0x18007f003  lea     edx, [rax+57h]; void *
0x18007f006  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x18007f00c  mov     ecx, 2
0x18007f011  call    cs:__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z; IsoGetWindowsMessageNumber(_IsoMsgWmNumbers)
0x18007f017  mov     r8, [rbp+arg_18]
0x18007f01b  cmp     edi, eax
0x18007f01d  setz    r14b
0x18007f021  cmp     dword ptr [r8+0Ch], 487h
0x18007f029  jnz     short loc_18007F045
0x18007f02b  cmp     edi, eax
0x18007f02d  jnz     short loc_18007F045
0x18007f02f  mov     rax, [rbx]
0x18007f032  mov     rcx, rbx
0x18007f035  mov     rax, [rax+38h]
0x18007f039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f03e  mov     edi, eax
0x18007f040  jmp     loc_18007F0E2
0x18007f045  mov     rax, [rbx]
0x18007f048  mov     dl, r14b
0x18007f04b  mov     r8d, [r8+4]
0x18007f04f  mov     rcx, rbx
0x18007f052  mov     edi, 1
0x18007f057  mov     rax, [rax]
0x18007f05a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f05f  test    al, al
0x18007f061  jz      short loc_18007F0E2
0x18007f063  mov     rax, [rbx]
0x18007f066  lea     r8, [rbp+arg_8]
0x18007f06a  mov     rdx, [rbp+arg_18]
0x18007f06e  mov     rcx, rbx
0x18007f071  mov     byte ptr [rbp+arg_8], 0
0x18007f075  mov     rax, [rax+18h]
0x18007f079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f07e  mov     edi, eax
0x18007f080  test    eax, eax
0x18007f082  js      short loc_18007F0AC
0x18007f084  cmp     byte ptr [rbp+arg_8], 0
0x18007f088  jnz     short loc_18007F0AC
0x18007f08a  mov     ecx, [rbp+arg_10]
0x18007f08d  mov     r8d, esi
0x18007f090  mov     rax, [rbx]
0x18007f093  mov     dl, r14b
0x18007f096  mov     r9, [rbp+arg_18]
0x18007f09a  mov     [rsp+40h+var_20], ecx
0x18007f09e  mov     rcx, rbx
0x18007f0a1  mov     rax, [rax+10h]
0x18007f0a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f0aa  mov     edi, eax
0x18007f0ac  test    edi, edi
0x18007f0ae  jnz     short loc_18007F0B6
0x18007f0b0  cmp     byte ptr [rbp+arg_8], dil
0x18007f0b4  jz      short loc_18007F0E2
0x18007f0b6  mov     rcx, [rbp+var_10]
0x18007f0ba  mov     ecx, [rcx+28h]
0x18007f0bd  call    cs:__imp_?IsoReleaseThread@@YAKK@Z; IsoReleaseThread(ulong)
0x18007f0c3  mov     rcx, [rbp+var_10]; this
0x18007f0c7  xor     edx, edx; void *
0x18007f0c9  call    ?SetAppObj@_IsoComponent@@QEAAXQEAX@Z; _IsoComponent::SetAppObj(void * const)
0x18007f0ce  mov     rax, [rbx]
0x18007f0d1  mov     edx, 1
0x18007f0d6  mov     rcx, rbx
0x18007f0d9  mov     rax, [rax+8]
0x18007f0dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f0e2  test    esi, esi
0x18007f0e4  jz      short loc_18007F0EE
0x18007f0e6  mov     ecx, esi
0x18007f0e8  call    cs:__imp_?IsoFreeMessageBuffer@@YAJK@Z; IsoFreeMessageBuffer(ulong)
0x18007f0ee  mov     eax, edi
0x18007f0f0  add     rsp, 40h
0x18007f0f4  pop     r14
0x18007f0f6  pop     rdi
0x18007f0f7  pop     rsi
0x18007f0f8  pop     rbx
0x18007f0f9  pop     rbp
0x18007f0fa  retn
```
