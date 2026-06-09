# CfGetSyncRootInfoByPath

- ea: `0x1800101a0`
- end: `0x18001028b`
- name: `CfGetSyncRootInfoByPath`
- size: `235`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000231e`
- `0x1800101a0`
- `0x18001035c`
- `0x180012c28`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800101e4`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800101e4`

## string_xrefs

- `0x180010215`: `CfpGetSyncRootInfoByPath Failed`

## pseudocode

```c
__int64 __fastcall CfGetSyncRootInfoByPath(__int64 a1, int a2, const WCHAR *a3, int a4, __int64 a5)
{
  const WCHAR *v6; // rsi
  const WCHAR *v10; // rbp
  int SyncRootInfoByPath; // eax
  unsigned int v12; // ebx
  const wchar_t *v13; // rcx
  unsigned __int64 UnbiasedTime; // [rsp+40h] [rbp-A8h] BYREF
  int v16; // [rsp+50h] [rbp-98h] BYREF
  const wchar_t *v17; // [rsp+58h] [rbp-90h]

  UnbiasedTime = 0;
  v6 = &SourceString;
  v10 = &SourceString;
  memset_0(&v16, 0, 0x58u);
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  SyncRootInfoByPath = CfpGetSyncRootInfoByPath(a1, a2, (_DWORD)a3, a4, a5);
  v12 = SyncRootInfoByPath;
  if ( SyncRootInfoByPath > -1 )
  {
    v13 = 0;
    if ( a2 == 1 )
    {
      v6 = a3 + 14;
      v10 = a3 + 270;
    }
    else if ( a2 == 2 )
    {
      v6 = a3 + 2;
      v10 = a3 + 258;
    }
  }
  else
  {
    v13 = L"CfpGetSyncRootInfoByPath Failed";
  }
  v17 = v13;
  TlmLogApiReliability(0x18u, 0, a1, v6, v10, UnbiasedTime, &v16, SyncRootInfoByPath);
  return v12;
}

```

## disassembly

```asm
0x1800101a0  push    rbx
0x1800101a2  push    rbp
0x1800101a3  push    rsi
0x1800101a4  push    rdi
0x1800101a5  push    r14
0x1800101a7  push    r15
0x1800101a9  sub     rsp, 0B8h
0x1800101b0  mov     r14d, edx
0x1800101b3  mov     [rsp+0E8h+UnbiasedTime], 0
0x1800101bc  xor     edx, edx; Val
0x1800101be  lea     rsi, SourceString
0x1800101c5  mov     rdi, r8
0x1800101c8  mov     r15, rcx
0x1800101cb  lea     rcx, [rsp+0E8h+var_98]; void *
0x1800101d0  mov     ebx, r9d
0x1800101d3  mov     rbp, rsi
0x1800101d6  lea     r8d, [rdx+58h]; Size
0x1800101da  call    memset_0
0x1800101df  lea     rcx, [rsp+0E8h+UnbiasedTime]; UnbiasedTime
0x1800101e4  call    cs:__imp_QueryUnbiasedInterruptTime
0x1800101eb  nop     dword ptr [rax+rax+00h]
0x1800101f0  mov     rax, [rsp+0E8h+arg_20]
0x1800101f8  mov     r9d, ebx
0x1800101fb  mov     r8, rdi
0x1800101fe  mov     [rsp+0E8h+var_C8], rax
0x180010203  mov     edx, r14d
0x180010206  mov     rcx, r15
0x180010209  call    CfpGetSyncRootInfoByPath
0x18001020e  mov     ebx, eax
0x180010210  cmp     eax, 0FFFFFFFFh
0x180010213  jg      short loc_18001021E
0x180010215  lea     rcx, aCfpgetsyncroot_0; "CfpGetSyncRootInfoByPath Failed"
0x18001021c  jmp     short loc_180010244
0x18001021e  xor     ecx, ecx
0x180010220  cmp     r14d, 1
0x180010224  jnz     short loc_180010233
0x180010226  lea     rsi, [rdi+1Ch]
0x18001022a  lea     rbp, [rdi+21Ch]
0x180010231  jmp     short loc_180010244
0x180010233  cmp     r14d, 2
0x180010237  jnz     short loc_180010244
0x180010239  lea     rsi, [rdi+4]
0x18001023d  lea     rbp, [rdi+204h]
0x180010244  mov     [rsp+0E8h+var_B0], ebx
0x180010248  lea     rax, [rsp+0E8h+var_98]
0x18001024d  mov     [rsp+0E8h+var_B8], rax
0x180010252  mov     r9, rsi
0x180010255  mov     rax, [rsp+0E8h+UnbiasedTime]
0x18001025a  mov     r8, r15
0x18001025d  mov     [rsp+0E8h+var_90], rcx
0x180010262  xor     edx, edx
0x180010264  mov     [rsp+0E8h+var_C0], rax
0x180010269  mov     ecx, 18h
0x18001026e  mov     [rsp+0E8h+var_C8], rbp
0x180010273  call    TlmLogApiReliability
0x180010278  mov     eax, ebx
0x18001027a  add     rsp, 0B8h
0x180010281  pop     r15
0x180010283  pop     r14
0x180010285  pop     rdi
0x180010286  pop     rsi
0x180010287  pop     rbp
0x180010288  pop     rbx
0x180010289  retn
```
