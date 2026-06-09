# CicBridge::CacheBackingStore(HWND__ *,IBackingStoreHolder *)

- ea: `0x180064c98`
- end: `0x180064da2`
- name: `?CacheBackingStore@CicBridge@@QEAA_NPEAUHWND__@@PEAUIBackingStoreHolder@@@Z`
- size: `266`
- prototype: `bool __fastcall(CicBridge *__hidden this, HWND, struct IBackingStoreHolder *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180064a40`

## callees

- `0x18001cc80`
- `0x180040694`
- `0x180064c98`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180064d46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180064d46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180064d3e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180064d3e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180064cbc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180064cbc`
- `USER32!SetWinEventHook` at `0x180064d72`
- `USER32!SetWinEventHook` at `0x180064d72`

## string_xrefs

- `0x180064d81`: `CicBridge::CreateBackingStore. Unable to install WinEvent hook`

## pseudocode

```c
char __fastcall CicBridge::CacheBackingStore(CicBridge *this, HWND a2, struct IBackingStoreHolder *a3)
{
  CVoidPtrArray *v3; // rax
  void **v6; // rbx
  __int64 v7; // rcx
  DWORD idThread; // ebx
  DWORD idProcess; // eax
  HWINEVENTHOOK v11; // rax

  v3 = (CVoidPtrArray *)*((_QWORD *)this + 2);
  if ( !v3 )
  {
    v3 = (CVoidPtrArray *)LocalAlloc(0x40u, 0x18u);
    if ( v3 )
    {
      *((_QWORD *)v3 + 2) = 0;
      *(_QWORD *)v3 = &CStructArray<char>::`vftable';
      *((_QWORD *)v3 + 1) = 0;
    }
    *((_QWORD *)this + 2) = v3;
    if ( !v3 )
      goto LABEL_6;
  }
  v6 = CVoidPtrArray::Append(v3, (int)a2);
  if ( v6 )
  {
    (*(void (__fastcall **)(struct IBackingStoreHolder *))(*(_QWORD *)a3 + 8LL))(a3);
    *v6 = a3;
    if ( !*((_QWORD *)this + 1) )
    {
      idThread = GetCurrentThreadId();
      idProcess = GetCurrentProcessId();
      v11 = SetWinEventHook(0x8001u, 0x8002u, g_hInst, CicBridge::WinEventProc, idProcess, idThread, 4u);
      *((_QWORD *)this + 1) = v11;
      if ( !v11 )
        CicTrace(2u, "CicBridge::CreateBackingStore. Unable to install WinEvent hook");
    }
    return 1;
  }
  else
  {
LABEL_6:
    v7 = *((_QWORD *)this + 2);
    if ( v7 )
    {
      if ( !*(_DWORD *)(v7 + 16) )
      {
        (**(void (__fastcall ***)(__int64, __int64))v7)(v7, 1);
        *((_QWORD *)this + 2) = 0;
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180064c98  mov     [rsp+arg_0], rbx
0x180064c9d  mov     [rsp+arg_8], rsi
0x180064ca2  push    rdi
0x180064ca3  sub     rsp, 40h
0x180064ca7  mov     rax, [rcx+10h]
0x180064cab  mov     rsi, r8
0x180064cae  mov     rdi, rcx
0x180064cb1  test    rax, rax
0x180064cb4  jnz     short loc_180064CEA
0x180064cb6  lea     edx, [rax+18h]; uBytes
0x180064cb9  lea     ecx, [rax+40h]; uFlags
0x180064cbc  call    cs:__imp_LocalAlloc
0x180064cc2  test    rax, rax
0x180064cc5  jz      short loc_180064CE1
0x180064cc7  lea     rcx, ??_7?$CStructArray@D@@6B@; const CStructArray<char>::`vftable'
0x180064cce  mov     qword ptr [rax+10h], 0
0x180064cd6  mov     [rax], rcx
0x180064cd9  mov     qword ptr [rax+8], 0
0x180064ce1  mov     [rdi+10h], rax
0x180064ce5  test    rax, rax
0x180064ce8  jz      short loc_180064CFA
0x180064cea  mov     rcx, rax; this
0x180064ced  call    ?Append@CVoidPtrArray@@QEAAPEAPEAXH@Z; CVoidPtrArray::Append(int)
0x180064cf2  mov     rbx, rax
0x180064cf5  test    rax, rax
0x180064cf8  jnz     short loc_180064D25
0x180064cfa  mov     rcx, [rdi+10h]
0x180064cfe  test    rcx, rcx
0x180064d01  jz      short loc_180064D21
0x180064d03  cmp     dword ptr [rcx+10h], 0
0x180064d07  jnz     short loc_180064D21
0x180064d09  mov     rax, [rcx]
0x180064d0c  mov     edx, 1
0x180064d11  mov     rax, [rax]
0x180064d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064d19  mov     qword ptr [rdi+10h], 0
0x180064d21  xor     al, al
0x180064d23  jmp     short loc_180064D92
0x180064d25  mov     rax, [rsi]
0x180064d28  mov     rcx, rsi
0x180064d2b  mov     rax, [rax+8]
0x180064d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064d34  mov     [rbx], rsi
0x180064d37  cmp     qword ptr [rdi+8], 0
0x180064d3c  jnz     short loc_180064D90
0x180064d3e  call    cs:__imp_GetCurrentThreadId
0x180064d44  mov     ebx, eax
0x180064d46  call    cs:__imp_GetCurrentProcessId
0x180064d4c  mov     r8, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hmodWinEventProc
0x180064d53  lea     r9, ?WinEventProc@CicBridge@@CAXPEAUHWINEVENTHOOK__@@KPEAUHWND__@@JJKK@Z; pfnWinEventProc
0x180064d5a  mov     edx, 8002h; eventMax
0x180064d5f  mov     [rsp+48h+dwFlags], 4; dwFlags
0x180064d67  mov     [rsp+48h+idThread], ebx; idThread
0x180064d6b  mov     [rsp+48h+idProcess], eax; idProcess
0x180064d6f  lea     ecx, [rdx-1]; eventMin
0x180064d72  call    cs:__imp_SetWinEventHook
0x180064d78  mov     [rdi+8], rax
0x180064d7c  test    rax, rax
0x180064d7f  jnz     short loc_180064D90
0x180064d81  lea     rdx, aCicbridgeCreat_0; "CicBridge::CreateBackingStore. Unable t"...
0x180064d88  lea     ecx, [rax+2]; unsigned int
0x180064d8b  call    ?CicTrace@@YAXKPEBDZZ; CicTrace(ulong,char const *,...)
0x180064d90  mov     al, 1
0x180064d92  mov     rbx, [rsp+48h+arg_0]
0x180064d97  mov     rsi, [rsp+48h+arg_8]
0x180064d9c  add     rsp, 40h
0x180064da0  pop     rdi
0x180064da1  retn
```
