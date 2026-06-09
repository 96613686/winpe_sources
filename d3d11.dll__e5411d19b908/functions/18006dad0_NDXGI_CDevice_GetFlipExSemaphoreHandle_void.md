# NDXGI::CDevice::GetFlipExSemaphoreHandle(void)

- ea: `0x18006dad0`
- end: `0x18006db7d`
- name: `?GetFlipExSemaphoreHandle@CDevice@NDXGI@@UEAAPEAXXZ`
- size: `173`
- prototype: `void *__fastcall(NDXGI::CDevice *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18006dad0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18006db25`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18006db25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006db32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006db32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006db6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006db6a`

## pseudocode

```c
void *__fastcall NDXGI::CDevice::GetFlipExSemaphoreHandle(NDXGI::CDevice *this)
{
  void *result; // rax
  unsigned int i; // edi
  LONG v4; // edx
  DWORD LastError; // ecx

  result = (void *)*((_QWORD *)this + 120);
  if ( !result )
  {
    for ( i = 0; i < 3; ++i )
    {
      v4 = *((_DWORD *)this + 236);
      *((_QWORD *)this + 121) = 1;
      *((_QWORD *)this + 120) = CreateSemaphoreExW(0, v4, 16, 0, 0, 0x100002u);
      LastError = GetLastError();
      result = (void *)*((_QWORD *)this + 120);
      if ( result )
      {
        if ( LastError != 183 )
        {
          *((_DWORD *)this + 244) = 0;
          return result;
        }
        CloseHandle(*((HANDLE *)this + 120));
        *((_QWORD *)this + 120) = 0;
      }
      else if ( LastError != 5 )
      {
        return 0;
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18006dad0  mov     [rsp+arg_0], rbx
0x18006dad5  push    rdi
0x18006dad6  sub     rsp, 30h
0x18006dada  mov     rax, [rcx+3C0h]
0x18006dae1  mov     rbx, rcx
0x18006dae4  test    rax, rax
0x18006dae7  jz      short loc_18006DAF4
0x18006dae9  mov     rbx, [rsp+38h+arg_0]
0x18006daee  add     rsp, 30h
0x18006daf2  pop     rdi
0x18006daf3  retn
0x18006daf4  xor     edi, edi
0x18006daf6  cmp     edi, 3
0x18006daf9  jnb     short loc_18006DB63
0x18006dafb  mov     edx, [rbx+3B0h]; lInitialCount
0x18006db01  xor     r9d, r9d; lpName
0x18006db04  mov     [rsp+38h+dwDesiredAccess], 100002h; dwDesiredAccess
0x18006db0c  xor     ecx, ecx; lpSemaphoreAttributes
0x18006db0e  mov     qword ptr [rbx+3C8h], 1
0x18006db19  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18006db21  lea     r8d, [r9+10h]; lMaximumCount
0x18006db25  call    cs:__imp_CreateSemaphoreExW
0x18006db2b  mov     [rbx+3C0h], rax
0x18006db32  call    cs:__imp_GetLastError
0x18006db38  mov     ecx, eax
0x18006db3a  mov     rax, [rbx+3C0h]
0x18006db41  test    rax, rax
0x18006db44  jz      short loc_18006DB5A
0x18006db46  cmp     ecx, 0B7h
0x18006db4c  jz      short loc_18006DB67
0x18006db4e  mov     dword ptr [rbx+3D0h], 0
0x18006db58  jmp     short loc_18006DAE9
0x18006db5a  cmp     ecx, 5
0x18006db5d  jnz     short loc_18006DB63
0x18006db5f  inc     edi
0x18006db61  jmp     short loc_18006DAF6
0x18006db63  xor     eax, eax
0x18006db65  jmp     short loc_18006DAE9
0x18006db67  mov     rcx, rax; hObject
0x18006db6a  call    cs:__imp_CloseHandle
0x18006db70  mov     qword ptr [rbx+3C0h], 0
0x18006db7b  jmp     short loc_18006DB5F
```
