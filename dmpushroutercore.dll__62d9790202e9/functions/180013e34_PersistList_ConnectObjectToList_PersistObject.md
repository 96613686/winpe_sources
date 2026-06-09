# PersistList::ConnectObjectToList(PersistObject *)

- ea: `0x180013e34`
- end: `0x180013f5c`
- name: `?ConnectObjectToList@PersistList@@AEAAJPEAVPersistObject@@@Z`
- size: `296`
- prototype: `__int64 __fastcall(PersistList *__hidden this, struct PersistObject *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180014f80`

## callees

- `0x1800039f0`
- `0x18000c63c`
- `0x180013e34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013eeb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013eeb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013ede`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013ede`
- `DMCmnUtils!CopyString` at `0x180013eb7`
- `DMCmnUtils!CopyString` at `0x180013eb7`
- `DMCmnUtils!InvStrCmpW` at `0x180013ef8`
- `DMCmnUtils!InvStrCmpW` at `0x180013ef8`

## pseudocode

```c
__int64 __fastcall PersistList::ConnectObjectToList(PersistList *this, struct PersistObject *a2)
{
  bool v2; // zf
  int v5; // esi
  const unsigned __int16 **v6; // r12
  __int64 i; // r15
  __int64 v8; // rbx
  struct _RTL_CRITICAL_SECTION *v9; // rdi
  const unsigned __int16 *v10; // rbx
  unsigned __int16 v12[8]; // [rsp+20h] [rbp-58h] BYREF
  __int128 v13; // [rsp+30h] [rbp-48h]

  v2 = *((_DWORD *)a2 + 5) == 0;
  *(_OWORD *)v12 = 0;
  v13 = 0;
  if ( !v2 )
    return (unsigned int)-2147024809;
  v6 = (const unsigned __int16 **)((char *)a2 + 24);
  if ( *((_QWORD *)a2 + 3) )
  {
    v5 = 0;
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 4); i = (unsigned int)(i + 1) )
    {
      v8 = *(_QWORD *)(*((_QWORD *)this + 1) + 8 * i);
      v9 = (struct _RTL_CRITICAL_SECTION *)(v8 + 32);
      EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 32));
      v10 = *(const unsigned __int16 **)(v8 + 24);
      LeaveCriticalSection(v9);
      if ( !InvStrCmpW(*v6, v10) )
        return (unsigned int)-2147024809;
    }
LABEL_10:
    ++*((_DWORD *)this + 6);
    *((_QWORD *)a2 + 9) = &PersistList::FlushObjectMemberWrapper;
    *((_QWORD *)a2 + 10) = &PersistList::DeleteObjectMemberWrapper;
    *((_QWORD *)a2 + 11) = this;
    *((_DWORD *)a2 + 5) = 1;
    return (unsigned int)v5;
  }
  v5 = StringCchPrintfW(v12, 0x10u, L"%d", *((unsigned int *)this + 6));
  if ( v5 >= 0 )
  {
    v5 = CopyString(v12, 0x10u, (unsigned __int16 **)v6);
    if ( v5 >= 0 )
      goto LABEL_10;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180013e34  mov     [rsp+arg_10], rbx
0x180013e39  mov     [rsp+arg_18], rbp
0x180013e3e  push    rsi
0x180013e3f  push    rdi
0x180013e40  push    r12
0x180013e42  push    r14
0x180013e44  push    r15
0x180013e46  sub     rsp, 50h
0x180013e4a  mov     rax, cs:__security_cookie
0x180013e51  xor     rax, rsp
0x180013e54  mov     [rsp+78h+var_38], rax
0x180013e59  cmp     dword ptr [rdx+14h], 0
0x180013e5d  xorps   xmm0, xmm0
0x180013e60  movups  xmmword ptr [rsp+78h+var_58], xmm0
0x180013e65  mov     rbp, rdx
0x180013e68  mov     r14, rcx
0x180013e6b  movups  [rsp+78h+var_48], xmm0
0x180013e70  jz      short loc_180013E7C
0x180013e72  mov     esi, 80070057h
0x180013e77  jmp     loc_180013F34
0x180013e7c  lea     r12, [rdx+18h]
0x180013e80  cmp     qword ptr [r12], 0
0x180013e85  jnz     short loc_180013EC5
0x180013e87  mov     r9d, [rcx+18h]
0x180013e8b  lea     r8, aD; "%d"
0x180013e92  mov     ebx, 10h
0x180013e97  lea     rcx, [rsp+78h+var_58]; unsigned __int16 *
0x180013e9c  mov     edx, ebx; unsigned __int64
0x180013e9e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013ea3  mov     esi, eax
0x180013ea5  test    eax, eax
0x180013ea7  js      loc_180013F34
0x180013ead  mov     r8, r12
0x180013eb0  lea     rcx, [rsp+78h+var_58]
0x180013eb5  mov     edx, ebx
0x180013eb7  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180013ebd  mov     esi, eax
0x180013ebf  test    eax, eax
0x180013ec1  js      short loc_180013F34
0x180013ec3  jmp     short loc_180013F0F
0x180013ec5  xor     esi, esi
0x180013ec7  xor     r15d, r15d
0x180013eca  cmp     [rcx+10h], esi
0x180013ecd  jbe     short loc_180013F0F
0x180013ecf  mov     rax, [r14+8]
0x180013ed3  mov     rbx, [rax+r15*8]
0x180013ed7  lea     rdi, [rbx+20h]
0x180013edb  mov     rcx, rdi; lpCriticalSection
0x180013ede  call    cs:__imp_EnterCriticalSection
0x180013ee4  mov     rbx, [rbx+18h]
0x180013ee8  mov     rcx, rdi; lpCriticalSection
0x180013eeb  call    cs:__imp_LeaveCriticalSection
0x180013ef1  mov     rcx, [r12]
0x180013ef5  mov     rdx, rbx
0x180013ef8  call    cs:__imp_?InvStrCmpW@@YAHPEBG0@Z; InvStrCmpW(ushort const *,ushort const *)
0x180013efe  test    eax, eax
0x180013f00  jz      loc_180013E72
0x180013f06  inc     r15d
0x180013f09  cmp     r15d, [r14+10h]
0x180013f0d  jb      short loc_180013ECF
0x180013f0f  inc     dword ptr [r14+18h]
0x180013f13  lea     rax, ?FlushObjectMemberWrapper@PersistList@@CAJPEAXPEAVPersistObject@@W4PERSIST_OBJECT_MEMBER_ID@2@@Z; PersistList::FlushObjectMemberWrapper(void *,PersistObject *,PersistObject::PERSIST_OBJECT_MEMBER_ID)
0x180013f1a  mov     [rbp+48h], rax
0x180013f1e  lea     rax, ?DeleteObjectMemberWrapper@PersistList@@CAJPEAXPEAVPersistObject@@W4PERSIST_OBJECT_MEMBER_ID@2@@Z; PersistList::DeleteObjectMemberWrapper(void *,PersistObject *,PersistObject::PERSIST_OBJECT_MEMBER_ID)
0x180013f25  mov     [rbp+50h], rax
0x180013f29  mov     [rbp+58h], r14
0x180013f2d  mov     dword ptr [rbp+14h], 1
0x180013f34  mov     eax, esi
0x180013f36  mov     rcx, [rsp+78h+var_38]
0x180013f3b  xor     rcx, rsp; StackCookie
0x180013f3e  call    __security_check_cookie
0x180013f43  lea     r11, [rsp+78h+var_28]
0x180013f48  mov     rbx, [r11+40h]
0x180013f4c  mov     rbp, [r11+48h]
0x180013f50  mov     rsp, r11
0x180013f53  pop     r15
0x180013f55  pop     r14
0x180013f57  pop     r12
0x180013f59  pop     rdi
0x180013f5a  pop     rsi
0x180013f5b  retn
```
