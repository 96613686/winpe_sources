# UserMiniCallback(void *,_MINIDUMP_CALLBACK_INPUT * const,_MINIDUMP_CALLBACK_OUTPUT *)

- ea: `0x1800e7500`
- end: `0x1800e7703`
- name: `?UserMiniCallback@@YAHPEAXQEAU_MINIDUMP_CALLBACK_INPUT@@PEAU_MINIDUMP_CALLBACK_OUTPUT@@@Z`
- size: `515`
- prototype: `__int64 __fastcall(void *, struct _MINIDUMP_CALLBACK_INPUT *const, struct _MINIDUMP_CALLBACK_OUTPUT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callees

- `0x1800727b8`
- `0x1800793cc`
- `0x180081918`
- `0x180098468`
- `0x1800e7500`
- `0x1800e8b30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7601`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7618`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7601`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7618`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e7560`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e7560`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800e7592`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800e7592`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e75d5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e75d5`

## string_xrefs

- `0x1800e763a`: `Unable to create kernel minidump file, %s\n`

## pseudocode

```c
__int64 __fastcall UserMiniCallback(
        void *a1,
        struct _MINIDUMP_CALLBACK_INPUT *const a2,
        struct _MINIDUMP_CALLBACK_OUTPUT *a3)
{
  ULONG CallbackType; // r8d
  ULONG v7; // r8d
  ULONG v8; // r8d
  ULONG v9; // r8d
  ULONG v10; // r8d
  void *v11; // rcx
  const WCHAR *v12; // rcx
  char *FileW; // rcx
  signed int LastError; // eax
  unsigned __int16 *v15; // rax
  struct ImageInfo *ImageByOffset; // rcx
  unsigned __int64 v18; // rdx

  CallbackType = a2->CallbackType;
  if ( CallbackType )
  {
    v7 = CallbackType - 3;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        v9 = v8 - 2;
        if ( v9 )
        {
          v10 = v9 - 1;
          if ( v10 )
          {
            if ( v10 == 1 )
            {
              v11 = (void *)*((_QWORD *)a1 + 12);
              if ( v11 )
              {
                CloseHandle(v11);
                v12 = (const WCHAR *)*((_QWORD *)a1 + 11);
                *((_QWORD *)a1 + 12) = 0;
                if ( a2->Status )
                  DeleteFileW(v12);
                else
                  dprintf(L"Wrote kernel minidump '%s'\n", v12);
              }
            }
          }
          else if ( (*((_BYTE *)a1 + 24) & 4) != 0 )
          {
            FileW = (char *)CreateFileW(*((LPCWSTR *)a1 + 11), 0x40000000u, 0, 0, 2u, 0x80u, 0);
            *((_QWORD *)a1 + 12) = FileW;
            if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
            {
              *((_QWORD *)a1 + 12) = 0;
              if ( GetLastError() )
              {
                LastError = GetLastError();
                if ( LastError > 0 )
                  LastError = (unsigned __int16)LastError | 0x80070000;
              }
              else
              {
                LastError = -2147467259;
              }
              v15 = FormatStatusCode(LastError);
              ErrOut(L"Unable to create kernel minidump file, %s\n", v15);
            }
            else
            {
              a3->MemoryBase = (ULONG64)FileW;
            }
          }
        }
        else
        {
          a3->Cancel = CheckUserInterruptInternal(0);
          a3->ModuleWriteFlags = 1;
        }
      }
      else if ( (*((_BYTE *)a1 + 24) & 1) != 0 )
      {
        a3->ModuleWriteFlags &= 1u;
      }
    }
    else if ( (*((_BYTE *)a1 + 24) & 1) != 0 )
    {
      if ( a2->Status != g_EventThreadSysId )
        return 0;
      a3->ModuleWriteFlags &= ~0x10u;
    }
  }
  else if ( (*((_BYTE *)a1 + 24) & 1) != 0 )
  {
    if ( (a3->ModuleWriteFlags & 0x10) == 0 )
      a3->ModuleWriteFlags = 0;
  }
  else if ( (*((_BYTE *)a1 + 24) & 8) != 0 )
  {
    ImageByOffset = ProcessInfo::FindImageByOffset(g_Process, a2->Module.BaseOfImage, 1, 0);
    if ( !ImageByOffset
      || ImageByOffset != *((struct ImageInfo **)g_Process + 37)
      && ((v18 = *((_QWORD *)ImageByOffset + 4), *((_QWORD *)a1 + 8) < v18)
       || *((_QWORD *)a1 + 8) > *((unsigned int *)ImageByOffset + 10) + v18 - 1) )
    {
      a3->ModuleWriteFlags &= ~2u;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800e7500  mov     [rsp+arg_0], rbx
0x1800e7505  mov     [rsp+arg_8], rsi
0x1800e750a  push    rdi
0x1800e750b  sub     rsp, 40h
0x1800e750f  mov     rbx, r8
0x1800e7512  mov     rsi, rdx
0x1800e7515  mov     r8d, [rdx+0Ch]
0x1800e7519  mov     rdi, rcx
0x1800e751c  test    r8d, r8d
0x1800e751f  jz      loc_1800E7689
0x1800e7525  sub     r8d, 3
0x1800e7529  jz      loc_1800E766F
0x1800e752f  sub     r8d, 1
0x1800e7533  jz      loc_1800E7660
0x1800e7539  sub     r8d, 2
0x1800e753d  jz      loc_1800E764B
0x1800e7543  sub     r8d, 1
0x1800e7547  jz      short loc_1800E75A3
0x1800e7549  cmp     r8d, 1
0x1800e754d  jnz     loc_1800E76ED
0x1800e7553  mov     rcx, [rcx+60h]; hObject
0x1800e7557  test    rcx, rcx
0x1800e755a  jz      loc_1800E76ED
0x1800e7560  call    cs:__imp_CloseHandle
0x1800e7567  nop     dword ptr [rax+rax+00h]
0x1800e756c  mov     rcx, [rdi+58h]; lpFileName
0x1800e7570  mov     qword ptr [rdi+60h], 0
0x1800e7578  cmp     dword ptr [rsi+10h], 0
0x1800e757c  jnz     short loc_1800E7592
0x1800e757e  mov     rdx, rcx
0x1800e7581  lea     rcx, aWroteKernelMin; "Wrote kernel minidump '%s'\n"
0x1800e7588  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1800e758d  jmp     loc_1800E76ED
0x1800e7592  call    cs:__imp_DeleteFileW
0x1800e7599  nop     dword ptr [rax+rax+00h]
0x1800e759e  jmp     loc_1800E76ED
0x1800e75a3  test    byte ptr [rcx+18h], 4
0x1800e75a7  jz      loc_1800E76ED
0x1800e75ad  mov     rcx, [rcx+58h]; lpFileName
0x1800e75b1  xor     r9d, r9d; lpSecurityAttributes
0x1800e75b4  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800e75bd  xor     r8d, r8d; dwShareMode
0x1800e75c0  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800e75c8  mov     edx, 40000000h; dwDesiredAccess
0x1800e75cd  mov     [rsp+48h+dwCreationDisposition], 2; dwCreationDisposition
0x1800e75d5  call    cs:__imp_CreateFileW
0x1800e75dc  nop     dword ptr [rax+rax+00h]
0x1800e75e1  mov     rcx, rax
0x1800e75e4  mov     [rdi+60h], rax
0x1800e75e8  dec     rax
0x1800e75eb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800e75ef  ja      short loc_1800E75F9
0x1800e75f1  mov     [rbx], rcx
0x1800e75f4  jmp     loc_1800E76ED
0x1800e75f9  mov     qword ptr [rdi+60h], 0
0x1800e7601  call    cs:__imp_GetLastError
0x1800e7608  nop     dword ptr [rax+rax+00h]
0x1800e760d  test    eax, eax
0x1800e760f  jnz     short loc_1800E7618
0x1800e7611  mov     eax, 80004005h
0x1800e7616  jmp     short loc_1800E7630
0x1800e7618  call    cs:__imp_GetLastError
0x1800e761f  nop     dword ptr [rax+rax+00h]
0x1800e7624  test    eax, eax
0x1800e7626  jle     short loc_1800E7630
0x1800e7628  movzx   eax, ax
0x1800e762b  or      eax, 80070000h
0x1800e7630  mov     ecx, eax; int
0x1800e7632  call    ?FormatStatusCode@@YAPEAGJ@Z; FormatStatusCode(long)
0x1800e7637  mov     rdx, rax
0x1800e763a  lea     rcx, aUnableToCreate; "Unable to create kernel minidump file, "...
0x1800e7641  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800e7646  jmp     loc_1800E76ED
0x1800e764b  xor     ecx, ecx; unsigned __int8
0x1800e764d  call    ?CheckUserInterruptInternal@@YAKE@Z; CheckUserInterruptInternal(uchar)
0x1800e7652  mov     [rbx+4], eax
0x1800e7655  mov     dword ptr [rbx], 1
0x1800e765b  jmp     loc_1800E76ED
0x1800e7660  test    byte ptr [rcx+18h], 1
0x1800e7664  jz      loc_1800E76ED
0x1800e766a  and     dword ptr [rbx], 1
0x1800e766d  jmp     short loc_1800E76ED
0x1800e766f  test    byte ptr [rcx+18h], 1
0x1800e7673  jz      short loc_1800E76ED
0x1800e7675  mov     eax, cs:?g_EventThreadSysId@@3KA; ulong g_EventThreadSysId
0x1800e767b  cmp     [rdx+10h], eax
0x1800e767e  jz      short loc_1800E7684
0x1800e7680  xor     eax, eax
0x1800e7682  jmp     short loc_1800E76F2
0x1800e7684  and     dword ptr [rbx], 0FFFFFFEFh
0x1800e7687  jmp     short loc_1800E76ED
0x1800e7689  test    byte ptr [rcx+18h], 1
0x1800e768d  jz      short loc_1800E769C
0x1800e768f  test    byte ptr [rbx], 10h
0x1800e7692  jnz     short loc_1800E76ED
0x1800e7694  mov     dword ptr [rbx], 0
0x1800e769a  jmp     short loc_1800E76ED
0x1800e769c  test    byte ptr [rcx+18h], 8
0x1800e76a0  jz      short loc_1800E76ED
0x1800e76a2  mov     rdx, [rdx+18h]; unsigned __int64
0x1800e76a6  xor     r9d, r9d; int
0x1800e76a9  mov     rcx, cs:?g_Process@@3PEAVProcessInfo@@EA; this
0x1800e76b0  lea     r8d, [r9+1]; int
0x1800e76b4  call    ?FindImageByOffset@ProcessInfo@@QEAAPEAVImageInfo@@_KHH@Z; ProcessInfo::FindImageByOffset(unsigned __int64,int,int)
0x1800e76b9  mov     rcx, rax
0x1800e76bc  test    rax, rax
0x1800e76bf  jz      short loc_1800E76EA
0x1800e76c1  mov     rax, cs:?g_Process@@3PEAVProcessInfo@@EA; ProcessInfo * g_Process
0x1800e76c8  cmp     rcx, [rax+128h]
0x1800e76cf  jz      short loc_1800E76ED
0x1800e76d1  mov     rdx, [rcx+20h]
0x1800e76d5  cmp     [rdi+40h], rdx
0x1800e76d9  jb      short loc_1800E76EA
0x1800e76db  mov     ecx, [rcx+28h]
0x1800e76de  dec     rdx
0x1800e76e1  add     rdx, rcx
0x1800e76e4  cmp     [rdi+40h], rdx
0x1800e76e8  jbe     short loc_1800E76ED
0x1800e76ea  and     dword ptr [rbx], 0FFFFFFFDh
0x1800e76ed  mov     eax, 1
0x1800e76f2  mov     rbx, [rsp+48h+arg_0]
0x1800e76f7  mov     rsi, [rsp+48h+arg_8]
0x1800e76fc  add     rsp, 40h
0x1800e7700  pop     rdi
0x1800e7701  retn
```
