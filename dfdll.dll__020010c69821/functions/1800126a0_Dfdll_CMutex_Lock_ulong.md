# Dfdll::CMutex::Lock(ulong)

- ea: `0x1800126a0`
- end: `0x1800126fd`
- name: `?Lock@CMutex@Dfdll@@UEAAJK@Z`
- size: `93`
- prototype: `int(Dfdll::CMutex *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800126a0`
- `0x180012748`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800126d0`
- `KERNEL32!GetLastError` at `0x1800126d0`
- `KERNEL32!WaitForSingleObject` at `0x1800126c5`
- `KERNEL32!WaitForSingleObject` at `0x1800126c5`

## pseudocode

```c
__int64 __fastcall Dfdll::CMutex::Lock(Dfdll::CMutex *this, DWORD a2)
{
  signed int MutexHandle; // ecx
  DWORD v4; // eax
  signed int LastError; // eax
  HANDLE hHandle; // [rsp+40h] [rbp+18h] BYREF

  hHandle = 0;
  MutexHandle = Dfdll::CMutex::get_MutexHandle(this, &hHandle);
  if ( MutexHandle >= 0 )
  {
    v4 = WaitForSingleObject(hHandle, a2);
    if ( v4 == -1 )
    {
      LastError = GetLastError();
      MutexHandle = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        return (unsigned int)LastError;
    }
    else
    {
      MutexHandle = 0;
      if ( v4 == 258 )
        return (unsigned int)-2147024638;
    }
  }
  return (unsigned int)MutexHandle;
}

```

## disassembly

```asm
0x1800126a0  push    rbx
0x1800126a2  sub     rsp, 20h
0x1800126a6  and     [rsp+28h+hHandle], 0
0x1800126ac  mov     ebx, edx
0x1800126ae  lea     rdx, [rsp+28h+hHandle]; void **
0x1800126b3  call    ?get_MutexHandle@CMutex@Dfdll@@IEAAJAEAPEAX@Z; Dfdll::CMutex::get_MutexHandle(void * &)
0x1800126b8  mov     ecx, eax
0x1800126ba  test    eax, eax
0x1800126bc  js      short loc_1800126F5
0x1800126be  mov     rcx, [rsp+28h+hHandle]; hHandle
0x1800126c3  mov     edx, ebx; dwMilliseconds
0x1800126c5  call    cs:__imp_WaitForSingleObject
0x1800126cb  cmp     eax, 0FFFFFFFFh
0x1800126ce  jnz     short loc_1800126E6
0x1800126d0  call    cs:__imp_GetLastError
0x1800126d6  movzx   ecx, ax
0x1800126d9  or      ecx, 80070000h
0x1800126df  test    eax, eax
0x1800126e1  cmovle  ecx, eax
0x1800126e4  jmp     short loc_1800126F5
0x1800126e6  xor     ecx, ecx
0x1800126e8  mov     edx, 80070102h
0x1800126ed  cmp     eax, 102h
0x1800126f2  cmovz   ecx, edx
0x1800126f5  mov     eax, ecx
0x1800126f7  add     rsp, 20h
0x1800126fb  pop     rbx
0x1800126fc  retn
```
