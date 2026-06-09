# _lambda_b4d29158ca76b2c35dcf2d61c7c2df91_::operator()

- ea: `0x14003a1f8`
- end: `0x14003a312`
- name: `_lambda_b4d29158ca76b2c35dcf2d61c7c2df91_::operator()`
- size: `282`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14003a050`
- `0x14003b9f0`

## callees

- `0x140003450`
- `0x14000d778`
- `0x14003a1f8`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x14003a27f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x14003a27f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x14003a2c1`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x14003a2c1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x14003a217`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x14003a217`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x14003a29e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x14003a29e`

## pseudocode

```c
int __fastcall lambda_b4d29158ca76b2c35dcf2d61c7c2df91_::operator()(__int64 a1)
{
  __int64 v2; // rcx
  int *v3; // rax
  struct _FILETIME FileTime; // [rsp+20h] [rbp-28h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+28h] [rbp-20h] BYREF

  GlobalUnlock(**(HGLOBAL **)(a1 + 40));
  ***(_DWORD ***)(a1 + 8) = **(_DWORD **)(a1 + 16);
  v3 = *(int **)(a1 + 24);
  if ( *v3 < 0 )
    LODWORD(v3) = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)(a1 + 48) + 64LL) + 16LL))(
                    *(_QWORD *)(*(_QWORD *)(a1 + 48) + 64LL),
                    0);
  if ( *(int *)(a1 + 32) < 0 )
  {
    v3 = *(int **)a1;
    v2 = *(_QWORD *)(*(_QWORD *)a1 + 2000LL);
    if ( v2 )
    {
      if ( *(_QWORD *)(v2 + 24) )
      {
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        FileTime = 0;
        SystemTimeToFileTime(&SystemTime, &FileTime);
        LODWORD(v3) = CompareFileTime(
                        &FileTime,
                        (const FILETIME *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 2000LL) + 24LL) + 72LL));
        if ( (_DWORD)v3 == 1 )
        {
          v3 = *(int **)(a1 + 24);
          *v3 = -2146762495;
        }
      }
    }
  }
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
    LODWORD(v3) = McTemplateU0qq_EventWriteTransfer(
                    v2,
                    OmaDmClientFunctionReturnValueEvent,
                    8,
                    **(unsigned int **)(a1 + 24));
  return (int)v3;
}

```

## disassembly

```asm
0x14003a1f8  push    rbx
0x14003a1fa  sub     rsp, 40h
0x14003a1fe  mov     rax, cs:__security_cookie
0x14003a205  xor     rax, rsp
0x14003a208  mov     [rsp+48h+var_10], rax
0x14003a20d  mov     rbx, rcx
0x14003a210  mov     rcx, [rcx+28h]
0x14003a214  mov     rcx, [rcx]; hMem
0x14003a217  call    cs:__imp_GlobalUnlock
0x14003a21e  nop     dword ptr [rax+rax+00h]
0x14003a223  mov     rax, [rbx+8]
0x14003a227  mov     r8, [rbx+10h]
0x14003a22b  mov     rdx, [rax]
0x14003a22e  mov     eax, [r8]
0x14003a231  mov     [rdx], eax
0x14003a233  mov     rax, [rbx+18h]
0x14003a237  cmp     dword ptr [rax], 0
0x14003a23a  jge     short loc_14003A252
0x14003a23c  mov     rax, [rbx+30h]
0x14003a240  xor     edx, edx
0x14003a242  mov     rcx, [rax+40h]
0x14003a246  mov     rax, [rcx]
0x14003a249  mov     rax, [rax+10h]
0x14003a24d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a252  cmp     dword ptr [rbx+20h], 0
0x14003a256  jge     loc_14003A2DC
0x14003a25c  mov     rax, [rbx]
0x14003a25f  mov     rcx, [rax+7D0h]
0x14003a266  test    rcx, rcx
0x14003a269  jz      short loc_14003A2DC
0x14003a26b  cmp     qword ptr [rcx+18h], 0
0x14003a270  jz      short loc_14003A2DC
0x14003a272  xorps   xmm0, xmm0
0x14003a275  lea     rcx, [rsp+48h+SystemTime]; lpSystemTime
0x14003a27a  movups  xmmword ptr [rsp+48h+SystemTime.wYear], xmm0
0x14003a27f  call    cs:__imp_GetSystemTime
0x14003a286  nop     dword ptr [rax+rax+00h]
0x14003a28b  lea     rdx, [rsp+48h+FileTime]; lpFileTime
0x14003a290  mov     qword ptr [rsp+48h+FileTime.dwLowDateTime], 0
0x14003a299  lea     rcx, [rsp+48h+SystemTime]; lpSystemTime
0x14003a29e  call    cs:__imp_SystemTimeToFileTime
0x14003a2a5  nop     dword ptr [rax+rax+00h]
0x14003a2aa  mov     rax, [rbx]
0x14003a2ad  mov     rcx, [rax+7D0h]
0x14003a2b4  mov     rdx, [rcx+18h]
0x14003a2b8  lea     rcx, [rsp+48h+FileTime]; lpFileTime1
0x14003a2bd  add     rdx, 48h ; 'H'; lpFileTime2
0x14003a2c1  call    cs:__imp_CompareFileTime
0x14003a2c8  nop     dword ptr [rax+rax+00h]
0x14003a2cd  cmp     eax, 1
0x14003a2d0  jnz     short loc_14003A2DC
0x14003a2d2  mov     rax, [rbx+18h]
0x14003a2d6  mov     dword ptr [rax], 800B0101h
0x14003a2dc  mov     r8d, 8
0x14003a2e2  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, r8b
0x14003a2e9  jz      short loc_14003A2FE
0x14003a2eb  mov     r9, [rbx+18h]
0x14003a2ef  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x14003a2f6  mov     r9d, [r9]
0x14003a2f9  call    McTemplateU0qq_EventWriteTransfer
0x14003a2fe  mov     rcx, [rsp+48h+var_10]
0x14003a303  xor     rcx, rsp; StackCookie
0x14003a306  call    __security_check_cookie
0x14003a30b  add     rsp, 40h
0x14003a30f  pop     rbx
0x14003a310  retn
```
