# CActiveXInstallBroker::RemoveExtractedFilesAndDirs(ushort *,sSESSION *)

- ea: `0x140005924`
- end: `0x1400059ea`
- name: `?RemoveExtractedFilesAndDirs@CActiveXInstallBroker@@QEAAJPEAGPEAUsSESSION@@@Z`
- size: `198`
- prototype: `int(CActiveXInstallBroker *__hidden this, unsigned __int16 *, struct sSESSION *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1400082a0`

## callees

- `0x140005924`
- `0x140009824`
- `0x140009cc4`
- `0x14000abd4`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1400059d2`
- `KERNEL32!LeaveCriticalSection` at `0x1400059d2`
- `KERNEL32!EnterCriticalSection` at `0x140005946`
- `KERNEL32!EnterCriticalSection` at `0x140005946`

## pseudocode

```c
__int64 __fastcall CActiveXInstallBroker::RemoveExtractedFilesAndDirs(
        CActiveXInstallBroker *this,
        unsigned __int16 *a2,
        struct sSESSION *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  unsigned int v7; // edi
  __int64 v8; // rdx
  int v9; // ecx
  int v10; // eax

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  if ( *(_DWORD *)this )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    if ( *((int *)this + 12) >= 4 )
    {
      if ( a2 )
      {
        v8 = *((_QWORD *)this + 8) - (_QWORD)a2;
        do
        {
          v9 = *(unsigned __int16 *)((char *)a2 + v8);
          v10 = *a2 - v9;
          if ( v10 )
            break;
          ++a2;
        }
        while ( v9 );
        if ( v10 || !FilesInFileList(a3, *((struct sFNAME **)this + 16)) )
        {
          v7 = -2147024891;
        }
        else if ( (int)DeleteExtractedFiles((char *)a3 + 32, *((struct sFNAME **)a3 + 2)) < 0 )
        {
          v7 = 0;
        }
        else
        {
          v7 = RemoveDirectoryAndChildren((const char *)a3 + 32);
        }
      }
      else
      {
        v7 = -2147024809;
      }
    }
    else
    {
      v7 = -2147019873;
    }
  }
  else
  {
    v7 = -2147024882;
  }
  if ( *(_DWORD *)this )
    LeaveCriticalSection(v3);
  return v7;
}

```

## disassembly

```asm
0x140005924  push    rbx
0x140005926  push    rbp
0x140005927  push    rsi
0x140005928  push    rdi
0x140005929  sub     rsp, 28h
0x14000592d  cmp     dword ptr [rcx], 0
0x140005930  lea     rbx, [rcx+8]
0x140005934  mov     rbp, r8
0x140005937  mov     rdi, rdx
0x14000593a  mov     rsi, rcx
0x14000593d  jz      loc_1400059C5
0x140005943  mov     rcx, rbx; lpCriticalSection
0x140005946  call    cs:__imp_EnterCriticalSection
0x14000594d  nop     dword ptr [rax+rax+00h]
0x140005952  cmp     dword ptr [rsi+30h], 4
0x140005956  jge     short loc_14000595F
0x140005958  mov     edi, 8007139Fh
0x14000595d  jmp     short loc_1400059CA
0x14000595f  test    rdi, rdi
0x140005962  jnz     short loc_14000596B
0x140005964  mov     edi, 80070057h
0x140005969  jmp     short loc_1400059CA
0x14000596b  mov     rdx, [rsi+40h]
0x14000596f  sub     rdx, rdi
0x140005972  movzx   eax, word ptr [rdi]
0x140005975  movzx   ecx, word ptr [rdi+rdx]
0x140005979  sub     eax, ecx
0x14000597b  jnz     short loc_140005985
0x14000597d  add     rdi, 2
0x140005981  test    ecx, ecx
0x140005983  jnz     short loc_140005972
0x140005985  test    eax, eax
0x140005987  jz      short loc_140005990
0x140005989  mov     edi, 80070005h
0x14000598e  jmp     short loc_1400059CA
0x140005990  mov     rdx, [rsi+80h]; struct sFNAME *
0x140005997  mov     rcx, rbp; struct sSESSION *
0x14000599a  call    ?FilesInFileList@@YAHPEAUsSESSION@@PEAUsFNAME@@@Z; FilesInFileList(sSESSION *,sFNAME *)
0x14000599f  test    eax, eax
0x1400059a1  jz      short loc_140005989
0x1400059a3  mov     rdx, [rbp+10h]; struct sFNAME *
0x1400059a7  lea     rcx, [rbp+20h]; char *
0x1400059ab  call    ?DeleteExtractedFiles@@YAJPEADPEAUsFNAME@@@Z; DeleteExtractedFiles(char *,sFNAME *)
0x1400059b0  test    eax, eax
0x1400059b2  js      short loc_1400059C1
0x1400059b4  lea     rcx, [rbp+20h]; char *
0x1400059b8  call    ?RemoveDirectoryAndChildren@@YAJPEBD@Z; RemoveDirectoryAndChildren(char const *)
0x1400059bd  mov     edi, eax
0x1400059bf  jmp     short loc_1400059CA
0x1400059c1  xor     edi, edi
0x1400059c3  jmp     short loc_1400059CA
0x1400059c5  mov     edi, 8007000Eh
0x1400059ca  cmp     dword ptr [rsi], 0
0x1400059cd  jz      short loc_1400059DE
0x1400059cf  mov     rcx, rbx; lpCriticalSection
0x1400059d2  call    cs:__imp_LeaveCriticalSection
0x1400059d9  nop     dword ptr [rax+rax+00h]
0x1400059de  mov     eax, edi
0x1400059e0  add     rsp, 28h
0x1400059e4  pop     rdi
0x1400059e5  pop     rsi
0x1400059e6  pop     rbp
0x1400059e7  pop     rbx
0x1400059e8  retn
```
