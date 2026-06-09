# IsValidReportPath

- ea: `0x1800547dc`
- end: `0x180054914`
- name: `IsValidReportPath`
- size: `312`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180052984`
- `0x180054d80`

## callees

- `0x1800229c4`
- `0x1800547dc`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x1800548ab`
- `KERNEL32!CompareStringOrdinal` at `0x1800548ab`
- `KERNEL32!LocalFree` at `0x1800548c7`
- `KERNEL32!LocalFree` at `0x1800548c7`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x180054884`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x180054884`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18005486c`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18005486c`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18005481a`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18005481a`

## pseudocode

```c
char __fastcall IsValidReportPath(unsigned __int16 *a1)
{
  char v2; // di
  PWSTR v3; // rcx
  unsigned __int64 v4; // rax
  unsigned __int64 v5; // rdx
  size_t v6; // rsi
  struct _EVENT_DESCRIPTOR v8; // [rsp+30h] [rbp-28h] BYREF
  PWSTR pszPath; // [rsp+60h] [rbp+8h] BYREF

  v2 = 0;
  pszPath = 0;
  if ( !a1 || !*a1 )
    goto LABEL_18;
  if ( PathAllocCanonicalize(a1, 0x40u, &pszPath) < 0 )
  {
LABEL_14:
    v3 = pszPath;
    goto LABEL_15;
  }
  v3 = pszPath;
  if ( !pszPath )
  {
LABEL_18:
    v8 = (struct _EVENT_DESCRIPTOR)TLS_E_INVALID_REPORT_PATH;
    TLSLogEventString_1(&v8, a1);
    return v2;
  }
  v4 = -1;
  do
    ++v4;
  while ( pszPath[v4] );
  v5 = -1;
  do
    ++v5;
  while ( *(&g_szReportDir + v5) );
  if ( v4 > v5 )
  {
    v6 = v4 + 1;
    if ( PathCchRemoveFileSpec(pszPath, v4 + 1) >= 0
      && PathCchAddBackslash(pszPath, v6) >= 0
      && CompareStringOrdinal(pszPath, -1, &g_szReportDir, -1, 1) == 2 )
    {
      v2 = 1;
    }
    goto LABEL_14;
  }
LABEL_15:
  if ( v3 )
  {
    LocalFree(v3);
    pszPath = 0;
  }
  if ( !v2 )
    goto LABEL_18;
  return v2;
}

```

## disassembly

```asm
0x1800547dc  mov     rax, rsp
0x1800547df  mov     [rax+10h], rbx
0x1800547e3  mov     [rax+18h], rbp
0x1800547e7  mov     [rax+20h], rsi
0x1800547eb  push    rdi
0x1800547ec  push    r14
0x1800547ee  push    r15
0x1800547f0  sub     rsp, 40h
0x1800547f4  xor     ebp, ebp
0x1800547f6  mov     rbx, rcx
0x1800547f9  movzx   edi, bpl
0x1800547fd  mov     [rax+8], rbp
0x180054801  test    rcx, rcx
0x180054804  jz      loc_1800548DD
0x18005480a  cmp     [rcx], bp
0x18005480d  jz      loc_1800548DD
0x180054813  lea     r8, [rax+8]; ppszPathOut
0x180054817  lea     edx, [rbp+40h]; dwFlags
0x18005481a  call    cs:__imp_PathAllocCanonicalize
0x180054821  nop     dword ptr [rax+rax+00h]
0x180054826  test    eax, eax
0x180054828  js      loc_1800548BD
0x18005482e  mov     rcx, [rsp+58h+pszPath]; pszPath
0x180054833  test    rcx, rcx
0x180054836  jz      loc_1800548DD
0x18005483c  or      r14, 0FFFFFFFFFFFFFFFFh
0x180054840  mov     rax, r14
0x180054843  inc     rax
0x180054846  cmp     [rcx+rax*2], bp
0x18005484a  jnz     short loc_180054843
0x18005484c  lea     r15, ?g_szReportDir@@3PAGA; ushort near * g_szReportDir
0x180054853  mov     rdx, r14
0x180054856  inc     rdx
0x180054859  cmp     [r15+rdx*2], bp
0x18005485e  jnz     short loc_180054856
0x180054860  cmp     rax, rdx
0x180054863  jbe     short loc_1800548C2
0x180054865  lea     rsi, [rax+1]
0x180054869  mov     rdx, rsi; cchPath
0x18005486c  call    cs:__imp_PathCchRemoveFileSpec
0x180054873  nop     dword ptr [rax+rax+00h]
0x180054878  test    eax, eax
0x18005487a  js      short loc_1800548BD
0x18005487c  mov     rcx, [rsp+58h+pszPath]; pszPath
0x180054881  mov     rdx, rsi; cchPath
0x180054884  call    cs:__imp_PathCchAddBackslash
0x18005488b  nop     dword ptr [rax+rax+00h]
0x180054890  test    eax, eax
0x180054892  js      short loc_1800548BD
0x180054894  mov     rcx, [rsp+58h+pszPath]; lpString1
0x180054899  mov     esi, 1
0x18005489e  mov     r9d, r14d; cchCount2
0x1800548a1  mov     [rsp+58h+bIgnoreCase], esi; bIgnoreCase
0x1800548a5  mov     r8, r15; lpString2
0x1800548a8  mov     edx, r14d; cchCount1
0x1800548ab  call    cs:__imp_CompareStringOrdinal
0x1800548b2  nop     dword ptr [rax+rax+00h]
0x1800548b7  cmp     eax, 2
0x1800548ba  cmovz   edi, esi
0x1800548bd  mov     rcx, [rsp+58h+pszPath]; hMem
0x1800548c2  test    rcx, rcx
0x1800548c5  jz      short loc_1800548D8
0x1800548c7  call    cs:__imp_LocalFree
0x1800548ce  nop     dword ptr [rax+rax+00h]
0x1800548d3  mov     [rsp+58h+pszPath], rbp
0x1800548d8  test    dil, dil
0x1800548db  jnz     short loc_1800548F7
0x1800548dd  movups  xmm0, cs:TLS_E_INVALID_REPORT_PATH
0x1800548e4  mov     rdx, rbx; unsigned __int16 *
0x1800548e7  lea     rcx, [rsp+58h+var_28]; struct _EVENT_DESCRIPTOR *
0x1800548ec  movdqu  xmmword ptr [rsp+58h+var_28.Id], xmm0
0x1800548f2  call    ?TLSLogEventString_1@@YAXU_EVENT_DESCRIPTOR@@PEBG@Z; TLSLogEventString_1(_EVENT_DESCRIPTOR,ushort const *)
0x1800548f7  mov     rbx, [rsp+58h+arg_8]
0x1800548fc  mov     al, dil
0x1800548ff  mov     rbp, [rsp+58h+arg_10]
0x180054904  mov     rsi, [rsp+58h+arg_18]
0x180054909  add     rsp, 40h
0x18005490d  pop     r15
0x18005490f  pop     r14
0x180054911  pop     rdi
0x180054912  retn
```
