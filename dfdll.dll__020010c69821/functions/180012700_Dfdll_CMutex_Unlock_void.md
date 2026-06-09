# Dfdll::CMutex::Unlock(void)

- ea: `0x180012700`
- end: `0x180012748`
- name: `?Unlock@CMutex@Dfdll@@UEAAJXZ`
- size: `72`
- prototype: `__int64 __fastcall(Dfdll::CMutex *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180012700`
- `0x180012748`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180012729`
- `KERNEL32!GetLastError` at `0x180012729`
- `KERNEL32!ReleaseMutex` at `0x18001271f`
- `KERNEL32!ReleaseMutex` at `0x18001271f`

## pseudocode

```c
__int64 __fastcall Dfdll::CMutex::Unlock(Dfdll::CMutex *this)
{
  signed int MutexHandle; // ecx
  signed int LastError; // eax
  HANDLE hMutex; // [rsp+38h] [rbp+10h] BYREF

  hMutex = 0;
  MutexHandle = Dfdll::CMutex::get_MutexHandle(this, &hMutex);
  if ( MutexHandle >= 0 )
  {
    if ( ReleaseMutex(hMutex) )
    {
      return 0;
    }
    else
    {
      LastError = GetLastError();
      MutexHandle = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        return (unsigned int)LastError;
    }
  }
  return (unsigned int)MutexHandle;
}

```

## disassembly

```asm
0x180012700  sub     rsp, 28h
0x180012704  and     [rsp+28h+hMutex], 0
0x18001270a  lea     rdx, [rsp+28h+hMutex]; void **
0x18001270f  call    ?get_MutexHandle@CMutex@Dfdll@@IEAAJAEAPEAX@Z; Dfdll::CMutex::get_MutexHandle(void * &)
0x180012714  mov     ecx, eax
0x180012716  test    eax, eax
0x180012718  js      short loc_180012741
0x18001271a  mov     rcx, [rsp+28h+hMutex]; hMutex
0x18001271f  call    cs:__imp_ReleaseMutex
0x180012725  test    eax, eax
0x180012727  jnz     short loc_18001273F
0x180012729  call    cs:__imp_GetLastError
0x18001272f  movzx   ecx, ax
0x180012732  or      ecx, 80070000h
0x180012738  test    eax, eax
0x18001273a  cmovle  ecx, eax
0x18001273d  jmp     short loc_180012741
0x18001273f  xor     ecx, ecx
0x180012741  mov     eax, ecx
0x180012743  add     rsp, 28h
0x180012747  retn
```
