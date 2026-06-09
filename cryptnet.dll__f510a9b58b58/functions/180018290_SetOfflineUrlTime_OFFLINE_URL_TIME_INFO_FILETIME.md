# SetOfflineUrlTime(_OFFLINE_URL_TIME_INFO *,_FILETIME *)

- ea: `0x180018290`
- end: `0x180018301`
- name: `?SetOfflineUrlTime@@YAXPEAU_OFFLINE_URL_TIME_INFO@@PEAU_FILETIME@@@Z`
- size: `113`
- prototype: `void __fastcall(struct _OFFLINE_URL_TIME_INFO *, struct _FILETIME *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008f80`
- `0x180017f70`
- `0x18001802c`

## callees

- `0x180018290`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800182ae`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800182ae`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800182c1`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800182c1`

## pseudocode

```c
void __fastcall SetOfflineUrlTime(struct _OFFLINE_URL_TIME_INFO *a1, struct _FILETIME *a2)
{
  int v4; // eax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp+10h] BYREF

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( !a2 || CompareFileTime(a2, &SystemTimeAsFileTime) <= 0 )
  {
    v4 = ++*(_DWORD *)a1;
    if ( *(_DWORD *)a1 > 6u )
      v4 = 6;
    *(_QWORD *)((char *)a1 + 4) = *(_QWORD *)&SystemTimeAsFileTime
                                + 10000000LL * *((unsigned int *)qword_18002A108 + (unsigned int)(v4 - 1));
  }
}

```

## disassembly

```asm
0x180018290  mov     [rsp+arg_0], rbx
0x180018295  push    rdi
0x180018296  sub     rsp, 20h
0x18001829a  mov     rdi, rcx
0x18001829d  mov     qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800182a6  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800182ab  mov     rbx, rdx
0x1800182ae  call    cs:__imp_GetSystemTimeAsFileTime
0x1800182b4  test    rbx, rbx
0x1800182b7  jz      short loc_1800182CB
0x1800182b9  lea     rdx, [rsp+28h+SystemTimeAsFileTime]; lpFileTime2
0x1800182be  mov     rcx, rbx; lpFileTime1
0x1800182c1  call    cs:__imp_CompareFileTime
0x1800182c7  test    eax, eax
0x1800182c9  jg      short loc_1800182F6
0x1800182cb  inc     dword ptr [rdi]
0x1800182cd  mov     ecx, 6
0x1800182d2  mov     eax, [rdi]
0x1800182d4  cmp     eax, ecx
0x1800182d6  cmova   eax, ecx
0x1800182d9  lea     ecx, [rax-1]
0x1800182dc  lea     rax, qword_18002A108
0x1800182e3  mov     eax, [rax+rcx*4]
0x1800182e6  imul    rcx, rax, 989680h
0x1800182ed  add     rcx, qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime]
0x1800182f2  mov     [rdi+4], rcx
0x1800182f6  mov     rbx, [rsp+28h+arg_0]
0x1800182fb  add     rsp, 20h
0x1800182ff  pop     rdi
0x180018300  retn
```
