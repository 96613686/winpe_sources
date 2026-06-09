# CIEAdminBrokerObject::DeleteExtractedFile(char const *)

- ea: `0x140007d00`
- end: `0x140007db3`
- name: `?DeleteExtractedFile@CIEAdminBrokerObject@@UEAAJPEBD@Z`
- size: `179`
- prototype: `int(CIEAdminBrokerObject *__hidden this, const char *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140007d00`
- `0x14000a5d4`

## import_xrefs

- `KERNEL32!SetFileAttributesA` at `0x140007d70`
- `KERNEL32!SetFileAttributesA` at `0x140007d70`
- `KERNEL32!LeaveCriticalSection` at `0x140007d9b`
- `KERNEL32!LeaveCriticalSection` at `0x140007d9b`
- `KERNEL32!DeleteFileA` at `0x140007d7f`
- `KERNEL32!DeleteFileA` at `0x140007d7f`
- `KERNEL32!EnterCriticalSection` at `0x140007d27`
- `KERNEL32!EnterCriticalSection` at `0x140007d27`

## pseudocode

```c
__int64 __fastcall CIEAdminBrokerObject::DeleteExtractedFile(CIEAdminBrokerObject *this, const char *a2)
{
  __int64 v2; // rdi
  unsigned int v4; // ebx

  v2 = *((_QWORD *)this + 2);
  v4 = -2147467259;
  if ( v2 )
  {
    if ( *(_DWORD *)v2 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 8));
      if ( *(int *)(v2 + 48) >= 4 )
      {
        if ( a2 )
        {
          if ( (unsigned int)IsInFileListA(a2, *(struct sFNAME **)(v2 + 128)) )
          {
            v4 = 0;
            SetFileAttributesA(a2, 0x80u);
            DeleteFileA(a2);
          }
          else
          {
            v4 = -2147024891;
          }
        }
        else
        {
          v4 = -2147024809;
        }
      }
      else
      {
        v4 = -2147019873;
      }
    }
    else
    {
      v4 = -2147024882;
    }
    if ( *(_DWORD *)v2 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 8));
  }
  return v4;
}

```

## disassembly

```asm
0x140007d00  push    rbx
0x140007d02  push    rbp
0x140007d03  push    rsi
0x140007d04  push    rdi
0x140007d05  sub     rsp, 28h
0x140007d09  mov     rdi, [rcx+10h]
0x140007d0d  mov     rsi, rdx
0x140007d10  mov     ebx, 80004005h
0x140007d15  test    rdi, rdi
0x140007d18  jz      loc_140007DA7
0x140007d1e  cmp     dword ptr [rdi], 0
0x140007d21  jz      short loc_140007D8D
0x140007d23  lea     rcx, [rdi+8]; lpCriticalSection
0x140007d27  call    cs:__imp_EnterCriticalSection
0x140007d2e  nop     dword ptr [rax+rax+00h]
0x140007d33  cmp     dword ptr [rdi+30h], 4
0x140007d37  jge     short loc_140007D40
0x140007d39  mov     ebx, 8007139Fh
0x140007d3e  jmp     short loc_140007D92
0x140007d40  test    rsi, rsi
0x140007d43  jnz     short loc_140007D4C
0x140007d45  mov     ebx, 80070057h
0x140007d4a  jmp     short loc_140007D92
0x140007d4c  mov     rdx, [rdi+80h]; struct sFNAME *
0x140007d53  mov     rcx, rsi; char *
0x140007d56  call    ?IsInFileListA@@YAHPEBDPEAUsFNAME@@@Z; IsInFileListA(char const *,sFNAME *)
0x140007d5b  test    eax, eax
0x140007d5d  jnz     short loc_140007D66
0x140007d5f  mov     ebx, 80070005h
0x140007d64  jmp     short loc_140007D92
0x140007d66  mov     edx, 80h; dwFileAttributes
0x140007d6b  mov     rcx, rsi; lpFileName
0x140007d6e  xor     ebx, ebx
0x140007d70  call    cs:__imp_SetFileAttributesA
0x140007d77  nop     dword ptr [rax+rax+00h]
0x140007d7c  mov     rcx, rsi; lpFileName
0x140007d7f  call    cs:__imp_DeleteFileA
0x140007d86  nop     dword ptr [rax+rax+00h]
0x140007d8b  jmp     short loc_140007D92
0x140007d8d  mov     ebx, 8007000Eh
0x140007d92  cmp     dword ptr [rdi], 0
0x140007d95  jz      short loc_140007DA7
0x140007d97  lea     rcx, [rdi+8]; lpCriticalSection
0x140007d9b  call    cs:__imp_LeaveCriticalSection
0x140007da2  nop     dword ptr [rax+rax+00h]
0x140007da7  mov     eax, ebx
0x140007da9  add     rsp, 28h
0x140007dad  pop     rdi
0x140007dae  pop     rsi
0x140007daf  pop     rbp
0x140007db0  pop     rbx
0x140007db1  retn
```
