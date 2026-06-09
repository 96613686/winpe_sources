# SipFile::GetSize(unsigned __int64 *)

- ea: `0x180004500`
- end: `0x18000456c`
- name: `?GetSize@SipFile@@QEAAKPEA_K@Z`
- size: `108`
- prototype: `unsigned int __fastcall(SipFile *__hidden this, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800025b0`
- `0x180003c70`

## callees

- `0x180004500`

## import_xrefs

- `KERNEL32!GetFileSizeEx` at `0x180004543`
- `KERNEL32!GetFileSizeEx` at `0x180004543`
- `KERNEL32!GetLastError` at `0x18000454d`
- `KERNEL32!GetLastError` at `0x18000454d`

## pseudocode

```c
__int64 __fastcall SipFile::GetSize(SipFile *this, LARGE_INTEGER *a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rax
  LARGE_INTEGER FileSize; // [rsp+38h] [rbp+10h] BYREF

  FileSize.QuadPart = 0;
  if ( a2 )
  {
    v4 = *((_QWORD *)this + 1);
    v3 = 0;
    a2->QuadPart = 0;
    if ( v4 )
    {
      a2->QuadPart = *(unsigned int *)(*(_QWORD *)(v4 + 112) + 4LL);
    }
    else if ( GetFileSizeEx(*((HANDLE *)this + 4), &FileSize) )
    {
      *a2 = FileSize;
    }
    else
    {
      return GetLastError();
    }
  }
  else
  {
    return 87;
  }
  return v3;
}

```

## disassembly

```asm
0x180004500  mov     [rsp+arg_0], rbx
0x180004505  push    rdi
0x180004506  sub     rsp, 20h
0x18000450a  mov     qword ptr [rsp+28h+FileSize], 0
0x180004513  mov     rdi, rdx
0x180004516  test    rdx, rdx
0x180004519  jnz     short loc_180004520
0x18000451b  lea     ebx, [rdx+57h]
0x18000451e  jmp     short loc_18000455F
0x180004520  mov     rax, [rcx+8]
0x180004524  xor     ebx, ebx
0x180004526  mov     [rdx], rbx
0x180004529  test    rax, rax
0x18000452c  jz      short loc_18000453A
0x18000452e  mov     rax, [rax+70h]
0x180004532  mov     ecx, [rax+4]
0x180004535  mov     [rdx], rcx
0x180004538  jmp     short loc_18000455F
0x18000453a  mov     rcx, [rcx+20h]; hFile
0x18000453e  lea     rdx, [rsp+28h+FileSize]; lpFileSize
0x180004543  call    cs:__imp_GetFileSizeEx
0x180004549  test    eax, eax
0x18000454b  jnz     short loc_180004557
0x18000454d  call    cs:__imp_GetLastError
0x180004553  mov     ebx, eax
0x180004555  jmp     short loc_18000455F
0x180004557  mov     rax, qword ptr [rsp+28h+FileSize]
0x18000455c  mov     [rdi], rax
0x18000455f  mov     eax, ebx
0x180004561  mov     rbx, [rsp+28h+arg_0]
0x180004566  add     rsp, 20h
0x18000456a  pop     rdi
0x18000456b  retn
```
