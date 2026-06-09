# CRun::AdvanceKillTime(_FILETIME)

- ea: `0x180019848`
- end: `0x180019876`
- name: `?AdvanceKillTime@CRun@@QEAAXU_FILETIME@@@Z`
- size: `46`
- prototype: `void __fastcall(CRun *__hidden this, struct _FILETIME)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180019678`

## callees

- `0x180019848`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001985e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001985e`

## pseudocode

```c
void __fastcall CRun::AdvanceKillTime(const FILETIME *this, FILETIME a2)
{
  FILETIME *v2; // rbx
  FILETIME FileTime1; // [rsp+38h] [rbp+10h] BYREF

  FileTime1 = a2;
  v2 = (FILETIME *)&this[5];
  if ( CompareFileTime(&FileTime1, this + 5) < 0 )
    *v2 = FileTime1;
}

```

## disassembly

```asm
0x180019848  mov     qword ptr [rsp+FileTime1.dwLowDateTime], rdx
0x18001984d  push    rbx
0x18001984e  sub     rsp, 20h
0x180019852  lea     rbx, [rcx+28h]
0x180019856  mov     rdx, rbx; lpFileTime2
0x180019859  lea     rcx, [rsp+28h+FileTime1]; lpFileTime1
0x18001985e  call    cs:__imp_CompareFileTime
0x180019864  test    eax, eax
0x180019866  jns     short loc_180019870
0x180019868  mov     rax, qword ptr [rsp+28h+FileTime1.dwLowDateTime]
0x18001986d  mov     [rbx], rax
0x180019870  add     rsp, 20h
0x180019874  pop     rbx
0x180019875  retn
```
