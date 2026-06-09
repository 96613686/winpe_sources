# SipFile::Close(void)

- ea: `0x180003424`
- end: `0x1800034cd`
- name: `?Close@SipFile@@QEAAKXZ`
- size: `169`
- prototype: `unsigned int __fastcall(SipFile *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800033c0`
- `0x180004834`

## callees

- `0x180001008`
- `0x180003424`
- `0x180004700`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180003447`
- `KERNEL32!CloseHandle` at `0x180003447`
- `KERNEL32!GetLastError` at `0x180003451`
- `KERNEL32!GetLastError` at `0x180003451`

## pseudocode

```c
__int64 __fastcall SipFile::Close(SipFile *this)
{
  DWORD LastError; // edi
  char *v3; // rcx
  void *v4; // rcx
  __int64 result; // rax

  LastError = 0;
  v3 = (char *)*((_QWORD *)this + 4);
  if ( v3 != *((char **)this + 3) && (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && !CloseHandle(v3) )
    LastError = GetLastError();
  v4 = (void *)*((_QWORD *)this + 5);
  if ( v4 )
    operator delete(v4);
  SipFile::InvalidateCache(this);
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 3) = -1;
  *((_QWORD *)this + 4) = -1;
  *((_WORD *)this + 48) = 0;
  result = LastError;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 14) = 9999;
  return result;
}

```

## disassembly

```asm
0x180003424  mov     [rsp+arg_0], rbx
0x180003429  push    rdi
0x18000342a  sub     rsp, 20h
0x18000342e  mov     rbx, rcx
0x180003431  xor     edi, edi
0x180003433  mov     rcx, [rcx+20h]; hObject
0x180003437  cmp     rcx, [rbx+18h]
0x18000343b  jz      short loc_180003459
0x18000343d  lea     rax, [rcx-1]
0x180003441  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003445  ja      short loc_180003459
0x180003447  call    cs:__imp_CloseHandle
0x18000344d  test    eax, eax
0x18000344f  jnz     short loc_180003459
0x180003451  call    cs:__imp_GetLastError
0x180003457  mov     edi, eax
0x180003459  mov     rcx, [rbx+28h]; Block
0x18000345d  test    rcx, rcx
0x180003460  jz      short loc_180003467
0x180003462  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003467  mov     rcx, rbx; this
0x18000346a  call    ?InvalidateCache@SipFile@@AEAAXXZ; SipFile::InvalidateCache(void)
0x18000346f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003473  mov     qword ptr [rbx+8], 0
0x18000347b  mov     [rbx+18h], rax
0x18000347f  mov     [rbx+20h], rax
0x180003483  xor     eax, eax
0x180003485  mov     [rbx+60h], ax
0x180003489  mov     eax, edi
0x18000348b  mov     qword ptr [rbx+10h], 0
0x180003493  mov     qword ptr [rbx+30h], 0
0x18000349b  mov     qword ptr [rbx+28h], 0
0x1800034a3  mov     qword ptr [rbx+40h], 0
0x1800034ab  mov     qword ptr [rbx+48h], 0
0x1800034b3  mov     qword ptr [rbx+58h], 0
0x1800034bb  mov     dword ptr [rbx+38h], 270Fh
0x1800034c2  mov     rbx, [rsp+28h+arg_0]
0x1800034c7  add     rsp, 20h
0x1800034cb  pop     rdi
0x1800034cc  retn
```
