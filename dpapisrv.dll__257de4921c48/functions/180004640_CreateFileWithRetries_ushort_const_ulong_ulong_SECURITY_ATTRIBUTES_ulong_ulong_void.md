# CreateFileWithRetries(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)

- ea: `0x180004640`
- end: `0x180004777`
- name: `?CreateFileWithRetries@@YAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z`
- size: `311`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, DWORD dwDesiredAccess, DWORD dwShareMode, struct _SECURITY_ATTRIBUTES *, DWORD dwCreationDisposition, DWORD dwFlagsAndAttributes)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003b98`
- `0x180004920`

## callees

- `0x180004640`
- `0x18002f6bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800046f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800046f0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800046ab`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800046ab`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180004734`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180004734`

## pseudocode

```c
__int64 __fastcall CreateFileWithRetries(
        LPCWSTR lpFileName,
        DWORD dwDesiredAccess,
        DWORD dwShareMode,
        struct _SECURITY_ATTRIBUTES *a4,
        DWORD dwCreationDisposition,
        DWORD dwFlagsAndAttributes)
{
  __int64 *v6; // r14
  unsigned int v9; // edi
  __int64 result; // rax
  DWORD LastError; // r13d
  int v13; // edx
  int v14; // r8d
  unsigned int v15; // [rsp+98h] [rbp+10h]

  v6 = qword_180041420;
  if ( (dwDesiredAccess & 0x40000000) == 0 )
    v6 = qword_180041408;
  v9 = 0;
  v15 = 0;
  if ( *(_DWORD *)v6 )
  {
    while ( 1 )
    {
      result = (__int64)CreateFileW(
                          lpFileName,
                          dwDesiredAccess,
                          dwShareMode,
                          0,
                          dwCreationDisposition,
                          dwFlagsAndAttributes,
                          0);
      if ( result != -1 )
        break;
      LastError = GetLastError();
      if ( LastError != 32 )
      {
        v9 = v15;
        goto LABEL_7;
      }
      Sleep(*((_DWORD *)v6 + v15++));
      if ( !*((_DWORD *)v6 + v15) )
      {
        v9 = v15;
        goto LABEL_7;
      }
    }
  }
  else
  {
    LastError = 32;
LABEL_7:
    SetLastError(LastError);
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
      WPP_SF_dSD(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v13, v14, v9, (__int64)lpFileName, LastError);
    return -1;
  }
  return result;
}

```

## disassembly

```asm
0x180004640  push    rbx
0x180004642  push    rbp
0x180004643  push    rsi
0x180004644  push    rdi
0x180004645  push    r12
0x180004647  push    r13
0x180004649  push    r14
0x18000464b  push    r15
0x18000464d  sub     rsp, 48h
0x180004651  bt      edx, 1Eh
0x180004655  lea     rax, qword_180041408
0x18000465c  lea     r14, qword_180041420
0x180004663  mov     r15d, r8d
0x180004666  cmovnb  r14, rax
0x18000466a  mov     ebp, edx
0x18000466c  xor     edi, edi
0x18000466e  mov     r12, rcx
0x180004671  mov     [rsp+88h+arg_8], edi
0x180004678  cmp     [r14], edi
0x18000467b  jz      loc_18000471A
0x180004681  mov     edi, [rsp+88h+arg_28]
0x180004688  mov     esi, [rsp+88h+arg_20]
0x18000468f  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x180004698  xor     r9d, r9d; lpSecurityAttributes
0x18000469b  mov     [rsp+88h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x18000469f  mov     r8d, r15d; dwShareMode
0x1800046a2  mov     edx, ebp; dwDesiredAccess
0x1800046a4  mov     [rsp+88h+dwCreationDisposition], esi; dwCreationDisposition
0x1800046a8  mov     rcx, r12; lpFileName
0x1800046ab  call    cs:__imp_CreateFileW
0x1800046b2  nop     dword ptr [rax+rax+00h]
0x1800046b7  mov     rbx, rax
0x1800046ba  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800046be  jz      short loc_1800046D2
0x1800046c0  add     rsp, 48h
0x1800046c4  pop     r15
0x1800046c6  pop     r14
0x1800046c8  pop     r13
0x1800046ca  pop     r12
0x1800046cc  pop     rdi
0x1800046cd  pop     rsi
0x1800046ce  pop     rbp
0x1800046cf  pop     rbx
0x1800046d0  retn
0x1800046d2  call    cs:__imp_GetLastError
0x1800046d9  nop     dword ptr [rax+rax+00h]
0x1800046de  mov     r13d, eax
0x1800046e1  cmp     eax, 20h ; ' '
0x1800046e4  jz      short loc_180004729
0x1800046e6  mov     edi, [rsp+88h+arg_8]
0x1800046ed  mov     ecx, r13d; dwErrCode
0x1800046f0  call    cs:__imp_SetLastError
0x1800046f7  nop     dword ptr [rax+rax+00h]
0x1800046fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180004703  lea     rax, WPP_GLOBAL_Control
0x18000470a  cmp     rcx, rax
0x18000470d  jz      short loc_180004715
0x18000470f  test    byte ptr [rcx+1Ch], 8
0x180004713  jnz     short loc_18000475F
0x180004715  mov     rax, rbx
0x180004718  jmp     short loc_1800046C0
0x18000471a  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180004721  mov     r13d, 20h ; ' '
0x180004727  jmp     short loc_1800046ED
0x180004729  mov     ecx, [rsp+88h+arg_8]
0x180004730  mov     ecx, [r14+rcx*4]; dwMilliseconds
0x180004734  call    cs:__imp_Sleep
0x18000473b  nop     dword ptr [rax+rax+00h]
0x180004740  mov     eax, [rsp+88h+arg_8]
0x180004747  inc     eax
0x180004749  mov     [rsp+88h+arg_8], eax
0x180004750  cmp     dword ptr [r14+rax*4], 0
0x180004755  jnz     loc_18000468F
0x18000475b  mov     edi, eax
0x18000475d  jmp     short loc_1800046ED
0x18000475f  mov     rcx, [rcx+10h]
0x180004763  mov     r9d, edi
0x180004766  mov     [rsp+88h+dwFlagsAndAttributes], r13d
0x18000476b  mov     qword ptr [rsp+88h+dwCreationDisposition], r12
0x180004770  call    WPP_SF_dSD
0x180004775  jmp     short loc_180004715
```
