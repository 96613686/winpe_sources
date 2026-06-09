# FaxRouteDeleteFile(ulong,ushort const *)

- ea: `0x140042b40`
- end: `0x140042cce`
- name: `?FaxRouteDeleteFile@@YAJKPEBG@Z`
- size: `398`
- prototype: `__int64 __fastcall(int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x140042b40`
- `0x140065dbc`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140042b5c`
- `KERNEL32!SetLastError` at `0x140042c2e`
- `KERNEL32!SetLastError` at `0x140042b5c`
- `KERNEL32!SetLastError` at `0x140042c2e`
- `KERNEL32!DeleteFileW` at `0x140042c63`
- `KERNEL32!DeleteFileW` at `0x140042c63`
- `KERNEL32!EnterCriticalSection` at `0x140042b71`
- `KERNEL32!EnterCriticalSection` at `0x140042b7e`
- `KERNEL32!EnterCriticalSection` at `0x140042bef`
- `KERNEL32!EnterCriticalSection` at `0x140042c8a`
- `KERNEL32!EnterCriticalSection` at `0x140042c97`
- `KERNEL32!EnterCriticalSection` at `0x140042b71`
- `KERNEL32!EnterCriticalSection` at `0x140042b7e`
- `KERNEL32!EnterCriticalSection` at `0x140042bef`
- `KERNEL32!EnterCriticalSection` at `0x140042c8a`
- `KERNEL32!EnterCriticalSection` at `0x140042c97`
- `KERNEL32!LeaveCriticalSection` at `0x140042baa`
- `KERNEL32!LeaveCriticalSection` at `0x140042bb7`
- `KERNEL32!LeaveCriticalSection` at `0x140042c16`
- `KERNEL32!LeaveCriticalSection` at `0x140042c37`
- `KERNEL32!LeaveCriticalSection` at `0x140042c7d`
- `KERNEL32!LeaveCriticalSection` at `0x140042caa`
- `KERNEL32!LeaveCriticalSection` at `0x140042cb7`
- `KERNEL32!LeaveCriticalSection` at `0x140042baa`
- `KERNEL32!LeaveCriticalSection` at `0x140042bb7`
- `KERNEL32!LeaveCriticalSection` at `0x140042c16`
- `KERNEL32!LeaveCriticalSection` at `0x140042c37`
- `KERNEL32!LeaveCriticalSection` at `0x140042c7d`
- `KERNEL32!LeaveCriticalSection` at `0x140042caa`
- `KERNEL32!LeaveCriticalSection` at `0x140042cb7`
- `msvcrt!_wcsicmp` at `0x140042bff`
- `msvcrt!_wcsicmp` at `0x140042bff`

## pseudocode

```c
__int64 __fastcall FaxRouteDeleteFile(int a1, const unsigned __int16 *a2)
{
  DWORD v4; // ecx
  struct _LIST_ENTRY *i; // rbx
  const wchar_t **Flink; // rdi
  unsigned int v8; // ebp
  const wchar_t *v9; // r12
  const wchar_t **v10; // rax
  const wchar_t *v11; // rdx
  const WCHAR *v12; // rcx

  if ( !a2 )
  {
    v4 = 87;
LABEL_3:
    SetLastError(v4);
    return 0xFFFFFFFFLL;
  }
  EnterCriticalSection(&g_CsJob);
  EnterCriticalSection(&g_CsQueue);
  for ( i = g_QueueListHead.Flink; i != &g_QueueListHead; i = i->Flink )
  {
    if ( LODWORD(i[2].Flink) == a1 )
      goto LABEL_10;
  }
  i = 0;
LABEL_10:
  LeaveCriticalSection(&g_CsQueue);
  LeaveCriticalSection(&g_CsJob);
  if ( !i )
  {
    v4 = 13;
    goto LABEL_3;
  }
  Flink = (const wchar_t **)i[106].Flink;
  if ( Flink == (const wchar_t **)&i[106] )
  {
    v4 = 18;
    goto LABEL_3;
  }
  v8 = 1;
  EnterCriticalSection((LPCRITICAL_SECTION)&i[107].Blink);
  while ( 1 )
  {
    v9 = *Flink;
    if ( !_wcsicmp(a2, Flink[2]) )
      break;
    ++v8;
    Flink = (const wchar_t **)v9;
    if ( v9 == (const wchar_t *)&i[106] )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)&i[107].Blink);
      v4 = 2;
      goto LABEL_3;
    }
  }
  if ( v8 == 1 )
  {
    SetLastError(0xDu);
    LeaveCriticalSection((LPCRITICAL_SECTION)&i[107].Blink);
    return 0xFFFFFFFFLL;
  }
  v10 = (const wchar_t **)Flink[1];
  v11 = *Flink;
  *v10 = *Flink;
  *((_QWORD *)v11 + 1) = v10;
  v12 = Flink[2];
  *Flink = 0;
  Flink[1] = 0;
  DeleteFileW(v12);
  pMemFree((LPVOID)Flink[2]);
  pMemFree(Flink);
  LeaveCriticalSection((LPCRITICAL_SECTION)&i[107].Blink);
  EnterCriticalSection(&g_CsJob);
  EnterCriticalSection(&g_CsQueue);
  --LODWORD(i[107].Flink);
  LeaveCriticalSection(&g_CsQueue);
  LeaveCriticalSection(&g_CsJob);
  return v8;
}

```

## disassembly

```asm
0x140042b40  push    rbx
0x140042b42  push    rbp
0x140042b43  push    rsi
0x140042b44  push    rdi
0x140042b45  push    r12
0x140042b47  push    r14
0x140042b49  push    r15
0x140042b4b  sub     rsp, 20h
0x140042b4f  mov     r15, rdx
0x140042b52  mov     edi, ecx
0x140042b54  test    rdx, rdx
0x140042b57  jnz     short loc_140042B6A
0x140042b59  lea     ecx, [rdx+57h]; dwErrCode
0x140042b5c  call    cs:__imp_SetLastError
0x140042b62  or      eax, 0FFFFFFFFh
0x140042b65  jmp     loc_140042CBF
0x140042b6a  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140042b71  call    cs:__imp_EnterCriticalSection
0x140042b77  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140042b7e  call    cs:__imp_EnterCriticalSection
0x140042b84  mov     rbx, cs:?g_QueueListHead@@3U_LIST_ENTRY@@A.Flink; _LIST_ENTRY g_QueueListHead ...
0x140042b8b  lea     rax, ?g_QueueListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_QueueListHead
0x140042b92  jmp     short loc_140042B9C
0x140042b94  cmp     [rbx+20h], edi
0x140042b97  jz      short loc_140042BA3
0x140042b99  mov     rbx, [rbx]
0x140042b9c  cmp     rbx, rax
0x140042b9f  jnz     short loc_140042B94
0x140042ba1  xor     ebx, ebx
0x140042ba3  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140042baa  call    cs:__imp_LeaveCriticalSection
0x140042bb0  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140042bb7  call    cs:__imp_LeaveCriticalSection
0x140042bbd  test    rbx, rbx
0x140042bc0  jnz     short loc_140042BC7
0x140042bc2  lea     ecx, [rbx+0Dh]
0x140042bc5  jmp     short loc_140042B5C
0x140042bc7  lea     r14, [rbx+6A0h]
0x140042bce  mov     rdi, [r14]
0x140042bd1  cmp     rdi, r14
0x140042bd4  jnz     short loc_140042BE0
0x140042bd6  mov     ecx, 12h
0x140042bdb  jmp     loc_140042B5C
0x140042be0  lea     rsi, [rbx+6B8h]
0x140042be7  mov     ebp, 1
0x140042bec  mov     rcx, rsi; lpCriticalSection
0x140042bef  call    cs:__imp_EnterCriticalSection
0x140042bf5  mov     rdx, [rdi+10h]; String2
0x140042bf9  mov     rcx, r15; String1
0x140042bfc  mov     r12, [rdi]
0x140042bff  call    cs:__imp__wcsicmp
0x140042c05  test    eax, eax
0x140042c07  jz      short loc_140042C26
0x140042c09  inc     ebp
0x140042c0b  mov     rdi, r12
0x140042c0e  cmp     r12, r14
0x140042c11  jnz     short loc_140042BF5
0x140042c13  mov     rcx, rsi; lpCriticalSection
0x140042c16  call    cs:__imp_LeaveCriticalSection
0x140042c1c  mov     ecx, 2
0x140042c21  jmp     loc_140042B5C
0x140042c26  cmp     ebp, 1
0x140042c29  jnz     short loc_140042C42
0x140042c2b  lea     ecx, [rbp+0Ch]; dwErrCode
0x140042c2e  call    cs:__imp_SetLastError
0x140042c34  mov     rcx, rsi; lpCriticalSection
0x140042c37  call    cs:__imp_LeaveCriticalSection
0x140042c3d  jmp     loc_140042B62
0x140042c42  mov     rax, [rdi+8]
0x140042c46  mov     rdx, [rdi]
0x140042c49  mov     [rax], rdx
0x140042c4c  mov     [rdx+8], rax
0x140042c50  mov     rcx, [rdi+10h]; lpFileName
0x140042c54  mov     qword ptr [rdi], 0
0x140042c5b  mov     qword ptr [rdi+8], 0
0x140042c63  call    cs:__imp_DeleteFileW
0x140042c69  mov     rcx, [rdi+10h]; lpMem
0x140042c6d  call    pMemFree
0x140042c72  mov     rcx, rdi; lpMem
0x140042c75  call    pMemFree
0x140042c7a  mov     rcx, rsi; lpCriticalSection
0x140042c7d  call    cs:__imp_LeaveCriticalSection
0x140042c83  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140042c8a  call    cs:__imp_EnterCriticalSection
0x140042c90  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140042c97  call    cs:__imp_EnterCriticalSection
0x140042c9d  dec     dword ptr [rbx+6B0h]
0x140042ca3  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140042caa  call    cs:__imp_LeaveCriticalSection
0x140042cb0  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140042cb7  call    cs:__imp_LeaveCriticalSection
0x140042cbd  mov     eax, ebp
0x140042cbf  add     rsp, 20h
0x140042cc3  pop     r15
0x140042cc5  pop     r14
0x140042cc7  pop     r12
0x140042cc9  pop     rdi
0x140042cca  pop     rsi
0x140042ccb  pop     rbp
0x140042ccc  pop     rbx
0x140042ccd  retn
```
