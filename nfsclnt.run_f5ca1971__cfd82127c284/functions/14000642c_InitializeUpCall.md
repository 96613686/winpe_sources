# InitializeUpCall

- ea: `0x14000642c`
- end: `0x140006575`
- name: `InitializeUpCall`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, service_task`

## callers

- `0x14000664c`

## callees

- `0x14000642c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400064ea`
- `KERNEL32!GetLastError` at `0x1400064ea`
- `KERNEL32!CreateEventW` at `0x140006462`
- `KERNEL32!CreateEventW` at `0x140006462`
- `KERNEL32!Sleep` at `0x1400064fe`
- `KERNEL32!Sleep` at `0x1400064fe`
- `KERNEL32!CreateFileW` at `0x1400064d4`
- `KERNEL32!CreateFileW` at `0x1400064d4`
- `KERNEL32!CreateThread` at `0x140006546`
- `KERNEL32!CreateThread` at `0x140006546`

## pseudocode

```c
__int64 InitializeUpCall()
{
  unsigned int v0; // ebx
  __int64 v1; // rdi
  char *EventW; // rax
  int i; // ebx
  __int64 result; // rax

  v0 = 0;
  do
  {
    v1 = 4120LL * v0;
    EventW = *(char **)((char *)&qword_140020B10 + v1);
    if ( EventW == (char *)-1LL )
    {
      EventW = (char *)CreateEventW(0, 0, 0, 0);
      *(HANDLE *)((char *)&qword_140020B10 + v1) = EventW;
    }
    if ( (unsigned __int64)(EventW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      *(HANDLE *)((char *)&qword_140020B10 + v1) = (HANDLE)-1LL;
      return 3221225473LL;
    }
    ++v0;
  }
  while ( !v0 );
  for ( i = 5; !NfsClntGlobals && *(&hObject + 1) == (HANDLE)-1LL && i; --i )
  {
    *(&hObject + 1) = CreateFileW(L"\\\\.\\NfsRdr", 0xC0000000, 7u, 0, 3u, 0x40000080u, 0);
    if ( *(&hObject + 1) != (HANDLE)-1LL )
    {
      result = 0;
      if ( !NfsClntGlobals && *(&hObject + 1) != (HANDLE)-1LL )
      {
        hHandle = CreateThread(0, 0, ServiceUpCallRequests, &hHandle, 0, &ThreadId);
        return 0;
      }
      return result;
    }
    if ( GetLastError() == 1255 )
      return 3221226239LL;
    Sleep(0xC8u);
  }
  return 3221225473LL;
}

```

## disassembly

```asm
0x14000642c  mov     [rsp+arg_0], rbx
0x140006431  mov     [rsp+arg_8], rdi
0x140006436  push    r14
0x140006438  sub     rsp, 40h
0x14000643c  xor     ebx, ebx
0x14000643e  mov     eax, ebx
0x140006440  lea     r14, qword_140020B10
0x140006447  imul    rdi, rax, 1018h
0x14000644e  mov     rax, [rdi+r14]
0x140006452  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140006456  jnz     short loc_14000646C
0x140006458  xor     r9d, r9d; lpName
0x14000645b  xor     r8d, r8d; bInitialState
0x14000645e  xor     edx, edx; bManualReset
0x140006460  xor     ecx, ecx; lpEventAttributes
0x140006462  call    cs:__imp_CreateEventW
0x140006468  mov     [rdi+r14], rax
0x14000646c  dec     rax
0x14000646f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140006473  ja      loc_140006557
0x140006479  inc     ebx
0x14000647b  cmp     ebx, 1
0x14000647e  jb      short loc_14000643E
0x140006480  mov     ebx, 5
0x140006485  cmp     cs:NfsClntGlobals, 0
0x14000648c  jnz     loc_14000655F
0x140006492  cmp     qword ptr cs:hObject+8, 0FFFFFFFFFFFFFFFFh
0x14000649a  jnz     loc_14000655F
0x1400064a0  test    ebx, ebx
0x1400064a2  jz      loc_14000655F
0x1400064a8  xor     r9d, r9d; lpSecurityAttributes
0x1400064ab  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1400064b4  mov     [rsp+48h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x1400064bc  lea     rcx, FileName; "\\\\.\\NfsRdr"
0x1400064c3  mov     edx, 0C0000000h; dwDesiredAccess
0x1400064c8  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1400064d0  lea     r8d, [r9+7]; dwShareMode
0x1400064d4  call    cs:__imp_CreateFileW
0x1400064da  mov     qword ptr cs:hObject+8, rax
0x1400064e1  mov     rcx, rax
0x1400064e4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400064e8  jnz     short loc_140006510
0x1400064ea  call    cs:__imp_GetLastError
0x1400064f0  cmp     eax, 4E7h
0x1400064f5  jz      short loc_140006509
0x1400064f7  dec     ebx
0x1400064f9  mov     ecx, 0C8h; dwMilliseconds
0x1400064fe  call    cs:__imp_Sleep
0x140006504  jmp     loc_140006485
0x140006509  mov     eax, 0C00002FFh
0x14000650e  jmp     short loc_140006564
0x140006510  xor     eax, eax
0x140006512  cmp     cs:NfsClntGlobals, eax
0x140006518  jnz     short loc_140006564
0x14000651a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000651e  jz      short loc_140006564
0x140006520  lea     rax, ThreadId
0x140006527  xor     edx, edx; dwStackSize
0x140006529  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], rax; lpThreadId
0x14000652e  lea     r9, hHandle; lpParameter
0x140006535  lea     r8, ServiceUpCallRequests; lpStartAddress
0x14000653c  mov     [rsp+48h+dwCreationDisposition], 0; dwCreationFlags
0x140006544  xor     ecx, ecx; lpThreadAttributes
0x140006546  call    cs:__imp_CreateThread
0x14000654c  mov     cs:hHandle, rax
0x140006553  xor     eax, eax
0x140006555  jmp     short loc_140006564
0x140006557  mov     qword ptr [rdi+r14], 0FFFFFFFFFFFFFFFFh
0x14000655f  mov     eax, 0C0000001h
0x140006564  mov     rbx, [rsp+48h+arg_0]
0x140006569  mov     rdi, [rsp+48h+arg_8]
0x14000656e  add     rsp, 40h
0x140006572  pop     r14
0x140006574  retn
```
