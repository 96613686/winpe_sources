# ExplicitDelayLoaderBase::LoadModule(ushort const *,long (*)(HINSTANCE__ *),ulong)

- ea: `0x180011880`
- end: `0x18001192d`
- name: `?LoadModule@ExplicitDelayLoaderBase@@IEAAJPEBGP6AJPEAUHINSTANCE__@@@ZK@Z`
- size: `173`
- prototype: `__int64 __fastcall(ExplicitDelayLoaderBase *__hidden this, const unsigned __int16 *, int (*)(HINSTANCE), unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180011850`

## callees

- `0x180008d5c`
- `0x1800117c8`
- `0x180011880`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18001191a`
- `msvcp_win!_Mtx_unlock` at `0x18001191a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800118c5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800118c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118ee`

## string_xrefs

- `0x1800118be`: `api-ms-win-appmodel-unlock-l1-1-0.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ExplicitDelayLoaderBase::LoadModule(
        ExplicitDelayLoaderBase *this,
        const unsigned __int16 *a2,
        int (*a3)(HINSTANCE))
{
  HMODULE Library; // rax
  signed int ProcAddresses; // ebx
  signed int LastError; // eax

  std::_Mutex_base::lock((std::_Mutex_base *)&ExplicitDelayLoaderBase::g_loaderLock);
  if ( AppmodelUnlockLoader::s_this )
  {
    if ( *(&AppmodelUnlockLoader::s_this + 1) )
      ProcAddresses = -2147467263;
    else
      ProcAddresses = 0;
  }
  else
  {
    AppmodelUnlockLoader::s_this = 257;
    Library = LoadLibraryExW(L"api-ms-win-appmodel-unlock-l1-1-0.dll", 0, 0x800u);
    qword_18001C4D0 = (__int64)Library;
    if ( Library )
    {
      ProcAddresses = AppmodelUnlockLoader::GetProcAddresses(Library);
      *(&AppmodelUnlockLoader::s_this + 1) = ProcAddresses < 0;
    }
    else
    {
      LastError = GetLastError();
      ProcAddresses = LastError;
      if ( LastError > 0 )
        ProcAddresses = (unsigned __int16)LastError | 0x80070000;
    }
  }
  _Mtx_unlock((_Mtx_t)&ExplicitDelayLoaderBase::g_loaderLock);
  return (unsigned int)ProcAddresses;
}

```

## disassembly

```asm
0x180011880  mov     [rsp+arg_0], rbx
0x180011885  mov     [rsp+arg_10], r8
0x18001188a  push    rdi
0x18001188b  sub     rsp, 20h
0x18001188f  lea     rdi, ?g_loaderLock@ExplicitDelayLoaderBase@@0Vmutex@std@@A; std::mutex ExplicitDelayLoaderBase::g_loaderLock
0x180011896  mov     [rsp+28h+arg_10], rdi
0x18001189b  mov     rcx, rdi; this
0x18001189e  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800118a3  nop
0x1800118a4  cmp     byte ptr cs:?s_this@AppmodelUnlockLoader@@0V1@A, 0; AppmodelUnlockLoader AppmodelUnlockLoader::s_this
0x1800118ab  jnz     short loc_180011905
0x1800118ad  mov     cs:?s_this@AppmodelUnlockLoader@@0V1@A, 101h; AppmodelUnlockLoader AppmodelUnlockLoader::s_this
0x1800118b6  xor     edx, edx; hFile
0x1800118b8  mov     r8d, 800h; dwFlags
0x1800118be  lea     rcx, aApiMsWinAppmod; "api-ms-win-appmodel-unlock-l1-1-0.dll"
0x1800118c5  call    cs:__imp_LoadLibraryExW
0x1800118cb  mov     cs:qword_18001C4D0, rax
0x1800118d2  test    rax, rax
0x1800118d5  jz      short loc_1800118EE
0x1800118d7  mov     rcx, rax; HINSTANCE
0x1800118da  call    ?GetProcAddresses@AppmodelUnlockLoader@@CAJPEAUHINSTANCE__@@@Z; AppmodelUnlockLoader::GetProcAddresses(HINSTANCE__ *)
0x1800118df  mov     ebx, eax
0x1800118e1  mov     ecx, eax
0x1800118e3  shr     ecx, 1Fh
0x1800118e6  mov     byte ptr cs:?s_this@AppmodelUnlockLoader@@0V1@A+1, cl; AppmodelUnlockLoader AppmodelUnlockLoader::s_this
0x1800118ec  jmp     short loc_180011917
0x1800118ee  call    cs:__imp_GetLastError
0x1800118f4  mov     ebx, eax
0x1800118f6  test    eax, eax
0x1800118f8  jle     short loc_180011917
0x1800118fa  movzx   ebx, ax
0x1800118fd  or      ebx, 80070000h
0x180011903  jmp     short loc_180011917
0x180011905  cmp     byte ptr cs:?s_this@AppmodelUnlockLoader@@0V1@A+1, 0; AppmodelUnlockLoader AppmodelUnlockLoader::s_this
0x18001190c  jz      short loc_180011915
0x18001190e  mov     ebx, 80004001h
0x180011913  jmp     short loc_180011917
0x180011915  xor     ebx, ebx
0x180011917  mov     rcx, rdi; _Mtx_t
0x18001191a  call    cs:__imp__Mtx_unlock
0x180011920  mov     eax, ebx
0x180011922  mov     rbx, [rsp+28h+arg_0]
0x180011927  add     rsp, 20h
0x18001192b  pop     rdi
0x18001192c  retn
```
