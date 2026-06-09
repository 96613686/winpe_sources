# CD3D12Device::GetFlipExSemaphoreHandle(void)

- ea: `0x180053160`
- end: `0x180053208`
- name: `?GetFlipExSemaphoreHandle@CD3D12Device@@UEAAPEAXXZ`
- size: `168`
- prototype: `void *__fastcall(CD3D12Device *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18002984c`
- `0x1800530c8`
- `0x180060374`

## callees

- `0x180053160`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800531aa`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800531aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800531b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800531b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800531d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800531d6`

## pseudocode

```c
void *__fastcall CD3D12Device::GetFlipExSemaphoreHandle(CD3D12Device *this)
{
  void *result; // rax
  unsigned int i; // edi
  DWORD LastError; // ecx

  result = (void *)*((_QWORD *)this + 17);
  if ( !result )
  {
    for ( i = 0; i < 3; ++i )
    {
      *((_QWORD *)this + 17) = CreateSemaphoreExW(0, *((_DWORD *)this + 37), 16, 0, 0, 0x100002u);
      LastError = GetLastError();
      result = (void *)*((_QWORD *)this + 17);
      if ( result )
      {
        if ( LastError != 183 )
        {
          *((_DWORD *)this + 36) = 0;
          return result;
        }
        CloseHandle(*((HANDLE *)this + 17));
        *((_QWORD *)this + 17) = 0;
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
0x180053160  mov     [rsp+arg_0], rbx
0x180053165  push    rdi
0x180053166  sub     rsp, 30h
0x18005316a  mov     rax, [rcx+88h]
0x180053171  mov     rbx, rcx
0x180053174  test    rax, rax
0x180053177  jz      short loc_180053184
0x180053179  mov     rbx, [rsp+38h+arg_0]
0x18005317e  add     rsp, 30h
0x180053182  pop     rdi
0x180053183  retn
0x180053184  xor     edi, edi
0x180053186  cmp     edi, 3
0x180053189  jnb     short loc_180053201
0x18005318b  mov     edx, [rbx+94h]; lInitialCount
0x180053191  xor     r9d, r9d; lpName
0x180053194  mov     [rsp+38h+dwDesiredAccess], 100002h; dwDesiredAccess
0x18005319c  xor     ecx, ecx; lpSemaphoreAttributes
0x18005319e  mov     [rsp+38h+dwFlags], 0; dwFlags
0x1800531a6  lea     r8d, [r9+10h]; lMaximumCount
0x1800531aa  call    cs:__imp_CreateSemaphoreExW
0x1800531b0  mov     [rbx+88h], rax
0x1800531b7  call    cs:__imp_GetLastError
0x1800531bd  mov     ecx, eax
0x1800531bf  mov     rax, [rbx+88h]
0x1800531c6  test    rax, rax
0x1800531c9  jz      short loc_1800531E9
0x1800531cb  cmp     ecx, 0B7h
0x1800531d1  jnz     short loc_1800531F2
0x1800531d3  mov     rcx, rax; hObject
0x1800531d6  call    cs:__imp_CloseHandle
0x1800531dc  mov     qword ptr [rbx+88h], 0
0x1800531e7  jmp     short loc_1800531EE
0x1800531e9  cmp     ecx, 5
0x1800531ec  jnz     short loc_180053201
0x1800531ee  inc     edi
0x1800531f0  jmp     short loc_180053186
0x1800531f2  mov     dword ptr [rbx+90h], 0
0x1800531fc  jmp     loc_180053179
0x180053201  xor     eax, eax
0x180053203  jmp     loc_180053179
```
