# PersistList::ConnectObjectToList(PersistObject *)

- ea: `0x180026d48`
- end: `0x180026e70`
- name: `?ConnectObjectToList@PersistList@@AEAAJPEAVPersistObject@@@Z`
- size: `296`
- prototype: `__int64 __fastcall(PersistList *__hidden this, struct PersistObject *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180028720`

## callees

- `0x180007f48`
- `0x180026d48`
- `0x18003b9a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026df2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026df2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026dff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026dff`
- `DMCmnUtils!CopyString` at `0x180026dcb`
- `DMCmnUtils!CopyString` at `0x180026dcb`
- `DMCmnUtils!InvStrCmpW` at `0x180026e0c`
- `DMCmnUtils!InvStrCmpW` at `0x180026e0c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180026d48  mov     [rsp+arg_10], rbx
0x180026d4d  mov     [rsp+arg_18], rbp
0x180026d52  push    rsi
0x180026d53  push    rdi
0x180026d54  push    r12
0x180026d56  push    r14
0x180026d58  push    r15
0x180026d5a  sub     rsp, 50h
0x180026d5e  mov     rax, cs:__security_cookie
0x180026d65  xor     rax, rsp
0x180026d68  mov     [rsp+78h+var_38], rax
0x180026d6d  cmp     dword ptr [rdx+14h], 0
0x180026d71  xorps   xmm0, xmm0
0x180026d74  movups  xmmword ptr [rsp+78h+var_58], xmm0
0x180026d79  mov     rbp, rdx
0x180026d7c  mov     r14, rcx
0x180026d7f  movups  [rsp+78h+var_48], xmm0
0x180026d84  jz      short loc_180026D90
0x180026d86  mov     esi, 80070057h
0x180026d8b  jmp     loc_180026E48
0x180026d90  lea     r12, [rdx+18h]
0x180026d94  cmp     qword ptr [r12], 0
0x180026d99  jnz     short loc_180026DD9
0x180026d9b  mov     r9d, [rcx+18h]
0x180026d9f  lea     r8, aD; "%d"
0x180026da6  mov     ebx, 10h
0x180026dab  lea     rcx, [rsp+78h+var_58]; unsigned __int16 *
0x180026db0  mov     edx, ebx; unsigned __int64
0x180026db2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026db7  mov     esi, eax
0x180026db9  test    eax, eax
0x180026dbb  js      loc_180026E48
0x180026dc1  mov     r8, r12
0x180026dc4  lea     rcx, [rsp+78h+var_58]
0x180026dc9  mov     edx, ebx
0x180026dcb  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180026dd1  mov     esi, eax
0x180026dd3  test    eax, eax
0x180026dd5  js      short loc_180026E48
0x180026dd7  jmp     short loc_180026E23
0x180026dd9  xor     esi, esi
0x180026ddb  xor     r15d, r15d
0x180026dde  cmp     [rcx+10h], esi
0x180026de1  jbe     short loc_180026E23
0x180026de3  mov     rax, [r14+8]
0x180026de7  mov     rbx, [rax+r15*8]
0x180026deb  lea     rdi, [rbx+20h]
0x180026def  mov     rcx, rdi; lpCriticalSection
0x180026df2  call    cs:__imp_EnterCriticalSection
0x180026df8  mov     rbx, [rbx+18h]
0x180026dfc  mov     rcx, rdi; lpCriticalSection
0x180026dff  call    cs:__imp_LeaveCriticalSection
0x180026e05  mov     rcx, [r12]
0x180026e09  mov     rdx, rbx
0x180026e0c  call    cs:__imp_?InvStrCmpW@@YAHPEBG0@Z; InvStrCmpW(ushort const *,ushort const *)
0x180026e12  test    eax, eax
0x180026e14  jz      loc_180026D86
0x180026e1a  inc     r15d
0x180026e1d  cmp     r15d, [r14+10h]
0x180026e21  jb      short loc_180026DE3
0x180026e23  inc     dword ptr [r14+18h]
0x180026e27  lea     rax, ?FlushObjectMemberWrapper@PersistList@@CAJPEAXPEAVPersistObject@@W4PERSIST_OBJECT_MEMBER_ID@2@@Z; PersistList::FlushObjectMemberWrapper(void *,PersistObject *,PersistObject::PERSIST_OBJECT_MEMBER_ID)
0x180026e2e  mov     [rbp+48h], rax
0x180026e32  lea     rax, ?DeleteObjectMemberWrapper@PersistList@@CAJPEAXPEAVPersistObject@@W4PERSIST_OBJECT_MEMBER_ID@2@@Z; PersistList::DeleteObjectMemberWrapper(void *,PersistObject *,PersistObject::PERSIST_OBJECT_MEMBER_ID)
0x180026e39  mov     [rbp+50h], rax
0x180026e3d  mov     [rbp+58h], r14
0x180026e41  mov     dword ptr [rbp+14h], 1
0x180026e48  mov     eax, esi
0x180026e4a  mov     rcx, [rsp+78h+var_38]
0x180026e4f  xor     rcx, rsp; StackCookie
0x180026e52  call    __security_check_cookie
0x180026e57  lea     r11, [rsp+78h+var_28]
0x180026e5c  mov     rbx, [r11+40h]
0x180026e60  mov     rbp, [r11+48h]
0x180026e64  mov     rsp, r11
0x180026e67  pop     r15
0x180026e69  pop     r14
0x180026e6b  pop     r12
0x180026e6d  pop     rdi
0x180026e6e  pop     rsi
0x180026e6f  retn
```
