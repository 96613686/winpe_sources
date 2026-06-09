# FveGetAuthMethodSidInformation

- ea: `0x180067340`
- end: `0x1800674a5`
- name: `FveGetAuthMethodSidInformation`
- size: `357`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180005410`
- `0x180007980`
- `0x180008d70`
- `0x1800090c0`
- `0x18000ba30`
- `0x1800205f0`
- `0x180067340`
- `0x1800855e0`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180067406`
- `ntdll!RtlLengthSid` at `0x180067406`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180067436`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180067436`

## pseudocode

```c
__int64 __fastcall FveGetAuthMethodSidInformation(
        __int64 a1,
        const struct _GUID *a2,
        unsigned __int16 *a3,
        void *a4,
        ULONG *a5)
{
  PVOID v9; // rcx
  int LockObjectFromHandleImpl; // ebx
  ULONG v11; // eax
  bool v12; // cf
  PSID Sid; // [rsp+28h] [rbp-50h] BYREF
  CFveApiBase *v15; // [rsp+30h] [rbp-48h] BYREF

  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 200, &WPP_21aca8766aba355e40648602aec702fc_Traceguids);
  v15 = 0;
  Sid = 0;
  if ( !a2 || !a5 )
    goto LABEL_10;
  if ( *a5 )
    goto LABEL_9;
  if ( a4 )
  {
LABEL_10:
    LockObjectFromHandleImpl = -2147024809;
    goto LABEL_19;
  }
  if ( *a5 )
  {
LABEL_9:
    if ( !a4 )
      goto LABEL_10;
  }
  LockObjectFromHandleImpl = CFveApiHandle::GetLockObjectFromHandleImpl(2, a1, &v15);
  if ( LockObjectFromHandleImpl >= 0 )
  {
    LockObjectFromHandleImpl = CFveApiBase::GetAuthMethodSidInformation(v15, a2, a3, &Sid);
    if ( LockObjectFromHandleImpl >= 0 )
    {
      v11 = RtlLengthSid(Sid);
      if ( a4 )
      {
        v12 = *a5 < v11;
        *a5 = v11;
        if ( v12 )
        {
          LockObjectFromHandleImpl = -2147024774;
        }
        else if ( !CopySid(v11, a4, Sid) )
        {
          LockObjectFromHandleImpl = GetLastHresultError();
        }
      }
      else
      {
        *a5 = v11;
      }
    }
  }
LABEL_19:
  CFveApiHandle::ReleaseLockedObjectImpl(v9, v15);
  if ( Sid )
    CFveApiBase::FastFree(Sid);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      201,
      &WPP_21aca8766aba355e40648602aec702fc_Traceguids,
      (unsigned int)LockObjectFromHandleImpl);
  return (unsigned int)LockObjectFromHandleImpl;
}

```

## disassembly

```asm
0x180067340  push    rbx
0x180067342  push    rsi
0x180067343  push    rdi
0x180067344  push    r13
0x180067346  push    r14
0x180067348  push    r15
0x18006734a  sub     rsp, 48h
0x18006734e  mov     rsi, r9
0x180067351  mov     r15, r8
0x180067354  mov     r14, rdx
0x180067357  mov     rbx, rcx
0x18006735a  lea     r13, WPP_GLOBAL_Control
0x180067361  mov     rcx, cs:WPP_GLOBAL_Control
0x180067368  cmp     rcx, r13
0x18006736b  jz      short loc_180067388
0x18006736d  test    byte ptr [rcx+1Ch], 10h
0x180067371  jz      short loc_180067388
0x180067373  mov     edx, 0C8h
0x180067378  lea     r8, WPP_21aca8766aba355e40648602aec702fc_Traceguids
0x18006737f  mov     rcx, [rcx+10h]
0x180067383  call    WPP_SF_
0x180067388  mov     [rsp+78h+var_48], 0
0x180067391  mov     [rsp+78h+Sid], 0
0x18006739a  test    r14, r14
0x18006739d  jz      short loc_1800673BF
0x18006739f  mov     rdi, [rsp+78h+arg_20]
0x1800673a7  test    rdi, rdi
0x1800673aa  jz      short loc_1800673BF
0x1800673ac  cmp     dword ptr [rdi], 0
0x1800673af  jnz     short loc_1800673BA
0x1800673b1  test    rsi, rsi
0x1800673b4  jnz     short loc_1800673BF
0x1800673b6  cmp     [rdi], esi
0x1800673b8  jz      short loc_1800673C6
0x1800673ba  test    rsi, rsi
0x1800673bd  jnz     short loc_1800673C6
0x1800673bf  mov     ebx, 80070057h
0x1800673c4  jmp     short loc_180067426
0x1800673c6  lea     r8, [rsp+78h+var_48]
0x1800673cb  mov     rdx, rbx
0x1800673ce  mov     ecx, 2
0x1800673d3  call    ?GetLockObjectFromHandleImpl@CFveApiHandle@@SAJW4_FVEAPI_OBJECT_TYPE@@PEAXPEAPEAX@Z; CFveApiHandle::GetLockObjectFromHandleImpl(_FVEAPI_OBJECT_TYPE,void *,void * *)
0x1800673d8  mov     ebx, eax
0x1800673da  mov     [rsp+78h+var_58], eax
0x1800673de  test    eax, eax
0x1800673e0  js      short loc_180067451
0x1800673e2  lea     r9, [rsp+78h+Sid]; void **
0x1800673e7  mov     r8, r15; unsigned __int16 *
0x1800673ea  mov     rdx, r14; struct _GUID *
0x1800673ed  mov     rcx, [rsp+78h+var_48]; this
0x1800673f2  call    ?GetAuthMethodSidInformation@CFveApiBase@@QEBAJPEBU_GUID@@PEAGPEAPEAX@Z; CFveApiBase::GetAuthMethodSidInformation(_GUID const *,ushort *,void * *)
0x1800673f7  mov     ebx, eax
0x1800673f9  mov     [rsp+78h+var_58], eax
0x1800673fd  test    eax, eax
0x1800673ff  js      short loc_180067451
0x180067401  mov     rcx, [rsp+78h+Sid]; Sid
0x180067406  call    cs:__imp_RtlLengthSid
0x18006740d  nop     dword ptr [rax+rax+00h]
0x180067412  test    rsi, rsi
0x180067415  jnz     short loc_18006741B
0x180067417  mov     [rdi], eax
0x180067419  jmp     short loc_180067451
0x18006741b  cmp     [rdi], eax
0x18006741d  mov     [rdi], eax
0x18006741f  jnb     short loc_18006742C
0x180067421  mov     ebx, 8007007Ah
0x180067426  mov     [rsp+78h+var_58], ebx
0x18006742a  jmp     short loc_180067451
0x18006742c  mov     r8, [rsp+78h+Sid]; pSourceSid
0x180067431  mov     rdx, rsi; pDestinationSid
0x180067434  mov     ecx, eax; nDestinationSidLength
0x180067436  call    cs:__imp_CopySid
0x18006743d  nop     dword ptr [rax+rax+00h]
0x180067442  test    eax, eax
0x180067444  jnz     short loc_180067451
0x180067446  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18006744b  mov     ebx, eax
0x18006744d  mov     [rsp+78h+var_58], eax
0x180067451  mov     rdx, [rsp+78h+var_48]
0x180067456  call    ?ReleaseLockedObjectImpl@CFveApiHandle@@SAXW4_FVEAPI_OBJECT_TYPE@@PEAV1@@Z; CFveApiHandle::ReleaseLockedObjectImpl(_FVEAPI_OBJECT_TYPE,CFveApiHandle *)
0x18006745b  mov     rcx, [rsp+78h+Sid]; lpMem
0x180067460  test    rcx, rcx
0x180067463  jz      short loc_18006746A
0x180067465  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18006746a  mov     rcx, cs:WPP_GLOBAL_Control
0x180067471  cmp     rcx, r13
0x180067474  jz      short loc_180067494
0x180067476  test    byte ptr [rcx+1Ch], 10h
0x18006747a  jz      short loc_180067494
0x18006747c  mov     edx, 0C9h
0x180067481  mov     r9d, ebx
0x180067484  lea     r8, WPP_21aca8766aba355e40648602aec702fc_Traceguids
0x18006748b  mov     rcx, [rcx+10h]
0x18006748f  call    WPP_SF_d
0x180067494  mov     eax, ebx
0x180067496  add     rsp, 48h
0x18006749a  pop     r15
0x18006749c  pop     r14
0x18006749e  pop     r13
0x1800674a0  pop     rdi
0x1800674a1  pop     rsi
0x1800674a2  pop     rbx
0x1800674a3  retn
0x180122554  push    rbp
0x180122556  sub     rsp, 20h
0x18012255a  mov     rbp, rdx
0x18012255d  mov     rdx, [rbp+30h]
0x180122561  call    ?ReleaseLockedObjectImpl@CFveApiHandle@@SAXW4_FVEAPI_OBJECT_TYPE@@PEAV1@@Z; CFveApiHandle::ReleaseLockedObjectImpl(_FVEAPI_OBJECT_TYPE,CFveApiHandle *)
0x180122566  mov     rcx, [rbp+28h]; lpMem
0x18012256a  test    rcx, rcx
0x18012256d  jz      short loc_180122575
0x18012256f  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x180122574  nop
0x180122575  add     rsp, 20h
0x180122579  pop     rbp
0x18012257a  retn
```
