# Pku2uRevertImpersonation(void *)

- ea: `0x1800178d0`
- end: `0x18001792e`
- name: `?Pku2uRevertImpersonation@@YAXPEAX@Z`
- size: `94`
- prototype: `void __fastcall(HANDLE Token)`
- caller_count: `7`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007f40`
- `0x180009070`
- `0x18000fc70`
- `0x180020238`
- `0x1800286bc`
- `0x18002a320`
- `0x180035dc0`

## callees

- `0x1800178d0`
- `0x180023ce0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800178d9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800178d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017901`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017901`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180017926`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180017926`

## pseudocode

```c
void __fastcall Pku2uRevertImpersonation(HANDLE Token)
{
  DWORD LastError; // eax

  if ( !SetThreadToken(0, Token) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_145765ada38d35d83bd68130d412160b_Traceguids, LastError);
    }
    RevertToSelf();
  }
}

```

## disassembly

```asm
0x1800178d0  sub     rsp, 28h
0x1800178d4  mov     rdx, rcx; Token
0x1800178d7  xor     ecx, ecx; Thread
0x1800178d9  call    cs:__imp_SetThreadToken
0x1800178df  test    eax, eax
0x1800178e1  jz      short loc_1800178E8
0x1800178e3  add     rsp, 28h
0x1800178e7  retn
0x1800178e8  mov     rax, cs:WPP_GLOBAL_Control
0x1800178ef  lea     rcx, WPP_GLOBAL_Control
0x1800178f6  cmp     rax, rcx
0x1800178f9  jz      short loc_180017926
0x1800178fb  test    byte ptr [rax+1Ch], 1
0x1800178ff  jz      short loc_180017926
0x180017901  call    cs:__imp_GetLastError
0x180017907  mov     rcx, cs:WPP_GLOBAL_Control
0x18001790e  lea     r8, WPP_145765ada38d35d83bd68130d412160b_Traceguids
0x180017915  mov     edx, 0Bh
0x18001791a  mov     r9d, eax
0x18001791d  mov     rcx, [rcx+10h]
0x180017921  call    WPP_SF_d
0x180017926  call    cs:__imp_RevertToSelf
0x18001792c  jmp     short loc_1800178E3
```
