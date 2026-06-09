# CacDecoding::DecodingThreadContext::Init(bool)

- ea: `0x18015a864`
- end: `0x18015a964`
- name: `?Init@DecodingThreadContext@CacDecoding@@QEAAJ_N@Z`
- size: `256`
- prototype: `__int64 __fastcall(CacDecoding::DecodingThreadContext *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18015a96c`

## callees

- `0x18007f094`
- `0x18015a864`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18015a93e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18015a93e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015a8c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015a94d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015a8c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015a94d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18015a881`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18015a8ee`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18015a881`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18015a8ee`

## pseudocode

```c
signed int __fastcall CacDecoding::DecodingThreadContext::Init(CacDecoding::DecodingThreadContext *this, char a2)
{
  signed int v2; // ebx
  HANDLE EventW; // rax
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  signed int LastError; // eax
  signed int result; // eax
  HANDLE v9; // rax
  HANDLE Thread; // rax

  v2 = 0;
  if ( !a2 )
    return v2;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 1) = EventW;
  if ( !EventW )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((char *)WPP_GLOBAL_Control + 28) >= 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_8;
    }
    v6 = 12;
LABEL_7:
    WPP_SF_(v5[2], v6, WPP_77f1326bb8863b8eefa123368bbff2ba_Traceguids);
LABEL_8:
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return v2;
  }
  v9 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 2) = v9;
  if ( !v9 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((char *)WPP_GLOBAL_Control + 28) >= 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_8;
    }
    v6 = 13;
    goto LABEL_7;
  }
  Thread = CreateThread(0, 0, CacDecoding::DecodingThreadContext::DecodeThreadProc, this, 0, (LPDWORD)this + 12);
  *((_QWORD *)this + 3) = Thread;
  if ( Thread )
    return v2;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18015a864  mov     [rsp+arg_0], rbx
0x18015a869  push    rdi
0x18015a86a  sub     rsp, 30h
0x18015a86e  xor     ebx, ebx
0x18015a870  mov     rdi, rcx
0x18015a873  test    dl, dl
0x18015a875  jz      short loc_18015A8D7
0x18015a877  xor     r9d, r9d; lpName
0x18015a87a  xor     r8d, r8d; bInitialState
0x18015a87d  xor     edx, edx; bManualReset
0x18015a87f  xor     ecx, ecx; lpEventAttributes
0x18015a881  call    cs:__imp_CreateEventW
0x18015a887  mov     [rdi+8], rax
0x18015a88b  test    rax, rax
0x18015a88e  jnz     short loc_18015A8E4
0x18015a890  mov     rcx, cs:WPP_GLOBAL_Control
0x18015a897  lea     rax, WPP_GLOBAL_Control
0x18015a89e  cmp     rcx, rax
0x18015a8a1  jz      short loc_18015A8C2
0x18015a8a3  test    byte ptr [rcx+1Ch], 80h
0x18015a8a7  jz      short loc_18015A8C2
0x18015a8a9  cmp     byte ptr [rcx+19h], 2
0x18015a8ad  jb      short loc_18015A8C2
0x18015a8af  lea     edx, [rbx+0Ch]
0x18015a8b2  mov     rcx, [rcx+10h]
0x18015a8b6  lea     r8, WPP_77f1326bb8863b8eefa123368bbff2ba_Traceguids
0x18015a8bd  call    WPP_SF_
0x18015a8c2  call    cs:__imp_GetLastError
0x18015a8c8  mov     ebx, eax
0x18015a8ca  test    eax, eax
0x18015a8cc  jle     short loc_18015A8D7
0x18015a8ce  movzx   ebx, ax
0x18015a8d1  or      ebx, 80070000h
0x18015a8d7  mov     eax, ebx
0x18015a8d9  mov     rbx, [rsp+38h+arg_0]
0x18015a8de  add     rsp, 30h
0x18015a8e2  pop     rdi
0x18015a8e3  retn
0x18015a8e4  xor     r9d, r9d; lpName
0x18015a8e7  xor     r8d, r8d; bInitialState
0x18015a8ea  xor     edx, edx; bManualReset
0x18015a8ec  xor     ecx, ecx; lpEventAttributes
0x18015a8ee  call    cs:__imp_CreateEventW
0x18015a8f4  mov     [rdi+10h], rax
0x18015a8f8  test    rax, rax
0x18015a8fb  jnz     short loc_18015A923
0x18015a8fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18015a904  lea     rax, WPP_GLOBAL_Control
0x18015a90b  cmp     rcx, rax
0x18015a90e  jz      short loc_18015A8C2
0x18015a910  test    byte ptr [rcx+1Ch], 80h
0x18015a914  jz      short loc_18015A8C2
0x18015a916  cmp     byte ptr [rcx+19h], 2
0x18015a91a  jb      short loc_18015A8C2
0x18015a91c  mov     edx, 0Dh
0x18015a921  jmp     short loc_18015A8B2
0x18015a923  lea     rax, [rdi+30h]
0x18015a927  mov     r9, rdi; lpParameter
0x18015a92a  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18015a92f  lea     r8, ?DecodeThreadProc@DecodingThreadContext@CacDecoding@@SAKPEAX@Z; lpStartAddress
0x18015a936  xor     edx, edx; dwStackSize
0x18015a938  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x18015a93c  xor     ecx, ecx; lpThreadAttributes
0x18015a93e  call    cs:__imp_CreateThread
0x18015a944  mov     [rdi+18h], rax
0x18015a948  test    rax, rax
0x18015a94b  jnz     short loc_18015A8D7
0x18015a94d  call    cs:__imp_GetLastError
0x18015a953  test    eax, eax
0x18015a955  jle     short loc_18015A8D9
0x18015a957  movzx   eax, ax
0x18015a95a  or      eax, 80070000h
0x18015a95f  jmp     loc_18015A8D9
```
