# DeleteRetriableSessions(ushort const *)

- ea: `0x14000f580`
- end: `0x14000f6af`
- name: `?DeleteRetriableSessions@@YAJPEBG@Z`
- size: `303`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001401c`

## callees

- `0x14000271f`
- `0x14000b708`
- `0x14000b774`
- `0x14000f580`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000f657`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000f671`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000f657`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000f671`
- `omadmapi!__imp_OmaDmGetInitiationInfo` at `0x14000f5f8`
- `omadmapi!__imp_OmaDmGetInitiationInfo` at `0x14000f5f8`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x14000f62a`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x14000f62a`
- `omadmapi!__imp_OmaDmCloseSession` at `0x14000f618`
- `omadmapi!__imp_OmaDmCloseSession` at `0x14000f618`
- `omadmapi!__imp_OmaDmEnumerateInitiationInfo` at `0x14000f5b2`
- `omadmapi!__imp_OmaDmEnumerateInitiationInfo` at `0x14000f5b2`

## pseudocode

```c
__int64 __fastcall DeleteRetriableSessions(const unsigned __int16 *a1)
{
  unsigned int v1; // esi
  int v3; // eax
  int InitiationInfo; // ebx
  __int64 i; // rdi
  HLOCAL *v6; // rax
  __int64 j; // rdi
  COmaDmPrcLogger *Logger; // rax
  _DWORD v10[16]; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v11; // [rsp+A8h] [rbp+38h] BYREF
  HLOCAL hMem; // [rsp+B0h] [rbp+40h] BYREF

  v1 = 0;
  hMem = 0;
  v11 = 0;
  v3 = OmaDmEnumerateInitiationInfo(a1, 1, &hMem, &v11);
  InitiationInfo = v3;
  if ( v3 == -2147023728 )
  {
    InitiationInfo = 0;
  }
  else if ( v3 >= 0 )
  {
    for ( i = 0; (unsigned int)i < v11; i = (unsigned int)(i + 1) )
    {
      memset_0(v10, 0, sizeof(v10));
      v10[0] = 64;
      InitiationInfo = OmaDmGetInitiationInfo(*((_QWORD *)hMem + i), v10);
      if ( InitiationInfo < 0 )
        break;
      if ( v10[5] == 6 )
      {
        InitiationInfo = OmaDmCloseSession(*((_QWORD *)hMem + i));
        OmaDmFreeInitiationInfo(v10);
        if ( InitiationInfo < 0 )
          break;
        ++v1;
      }
    }
  }
  v6 = (HLOCAL *)hMem;
  if ( hMem )
  {
    for ( j = 0; (unsigned int)j < v11; j = (unsigned int)(j + 1) )
    {
      LocalFree(v6[j]);
      v6 = (HLOCAL *)hMem;
    }
    LocalFree(v6);
  }
  Logger = COmaDmPrcLogger::GetLogger();
  COmaDmPrcLogger::LogOmaDmPrcDeleteRetriableSessions(Logger, a1, v1, v11, InitiationInfo);
  return (unsigned int)InitiationInfo;
}

```

## disassembly

```asm
0x14000f580  mov     [rsp-28h+arg_0], rbx
0x14000f585  push    rbp
0x14000f586  push    rsi
0x14000f587  push    rdi
0x14000f588  push    r14
0x14000f58a  push    r15
0x14000f58c  mov     rbp, rsp
0x14000f58f  sub     rsp, 70h
0x14000f593  xor     esi, esi
0x14000f595  mov     [rbp+hMem], 0
0x14000f59d  lea     r9, [rbp+arg_8]
0x14000f5a1  mov     [rbp+arg_8], 0
0x14000f5a8  lea     r8, [rbp+hMem]
0x14000f5ac  mov     r15, rcx
0x14000f5af  lea     edx, [rsi+1]
0x14000f5b2  call    cs:__imp_OmaDmEnumerateInitiationInfo
0x14000f5b9  nop     dword ptr [rax+rax+00h]
0x14000f5be  mov     ebx, eax
0x14000f5c0  cmp     eax, 80070490h
0x14000f5c5  jnz     short loc_14000F5CB
0x14000f5c7  xor     ebx, ebx
0x14000f5c9  jmp     short loc_14000F643
0x14000f5cb  test    eax, eax
0x14000f5cd  js      short loc_14000F643
0x14000f5cf  xor     edi, edi
0x14000f5d1  cmp     [rbp+arg_8], esi
0x14000f5d4  jbe     short loc_14000F643
0x14000f5d6  xor     edx, edx; Val
0x14000f5d8  lea     rcx, [rbp+var_40]; void *
0x14000f5dc  lea     r8d, [rdx+40h]; Size
0x14000f5e0  call    memset_0
0x14000f5e5  mov     rcx, [rbp+hMem]
0x14000f5e9  lea     rdx, [rbp+var_40]
0x14000f5ed  mov     [rbp+var_40], 40h ; '@'
0x14000f5f4  mov     rcx, [rcx+rdi*8]
0x14000f5f8  call    cs:__imp_OmaDmGetInitiationInfo
0x14000f5ff  nop     dword ptr [rax+rax+00h]
0x14000f604  mov     ebx, eax
0x14000f606  test    eax, eax
0x14000f608  js      short loc_14000F643
0x14000f60a  cmp     [rbp+var_2C], 6
0x14000f60e  jnz     short loc_14000F63C
0x14000f610  mov     rcx, [rbp+hMem]
0x14000f614  mov     rcx, [rcx+rdi*8]
0x14000f618  call    cs:__imp_OmaDmCloseSession
0x14000f61f  nop     dword ptr [rax+rax+00h]
0x14000f624  lea     rcx, [rbp+var_40]
0x14000f628  mov     ebx, eax
0x14000f62a  call    cs:__imp_OmaDmFreeInitiationInfo
0x14000f631  nop     dword ptr [rax+rax+00h]
0x14000f636  test    ebx, ebx
0x14000f638  js      short loc_14000F643
0x14000f63a  inc     esi
0x14000f63c  inc     edi
0x14000f63e  cmp     edi, [rbp+arg_8]
0x14000f641  jb      short loc_14000F5D6
0x14000f643  mov     rax, [rbp+hMem]
0x14000f647  test    rax, rax
0x14000f64a  jz      short loc_14000F67D
0x14000f64c  xor     edi, edi
0x14000f64e  cmp     [rbp+arg_8], edi
0x14000f651  jbe     short loc_14000F66E
0x14000f653  mov     rcx, [rax+rdi*8]; hMem
0x14000f657  call    cs:__imp_LocalFree
0x14000f65e  nop     dword ptr [rax+rax+00h]
0x14000f663  mov     rax, [rbp+hMem]
0x14000f667  inc     edi
0x14000f669  cmp     edi, [rbp+arg_8]
0x14000f66c  jb      short loc_14000F653
0x14000f66e  mov     rcx, rax; hMem
0x14000f671  call    cs:__imp_LocalFree
0x14000f678  nop     dword ptr [rax+rax+00h]
0x14000f67d  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x14000f682  mov     r9d, [rbp+arg_8]; unsigned int
0x14000f686  mov     r8d, esi; unsigned int
0x14000f689  mov     rdx, r15; unsigned __int16 *
0x14000f68c  mov     [rsp+70h+var_50], ebx; int
0x14000f690  mov     rcx, rax; this
0x14000f693  call    ?LogOmaDmPrcDeleteRetriableSessions@COmaDmPrcLogger@@QEAAXPEBGKKJ@Z; COmaDmPrcLogger::LogOmaDmPrcDeleteRetriableSessions(ushort const *,ulong,ulong,long)
0x14000f698  mov     eax, ebx
0x14000f69a  mov     rbx, [rsp+70h+arg_0]
0x14000f6a2  add     rsp, 70h
0x14000f6a6  pop     r15
0x14000f6a8  pop     r14
0x14000f6aa  pop     rdi
0x14000f6ab  pop     rsi
0x14000f6ac  pop     rbp
0x14000f6ad  retn
```
