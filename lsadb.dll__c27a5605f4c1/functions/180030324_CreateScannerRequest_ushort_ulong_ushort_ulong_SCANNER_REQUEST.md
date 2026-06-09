# CreateScannerRequest(ushort *,ulong,ushort *,ulong,_SCANNER_REQUEST * *)

- ea: `0x180030324`
- end: `0x1800303dc`
- name: `?CreateScannerRequest@@YAJPEAGK0KPEAPEAU_SCANNER_REQUEST@@@Z`
- size: `184`
- prototype: `__int64 __fastcall(unsigned __int16 *, int, unsigned __int16 *, int, struct _SCANNER_REQUEST **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800311f8`

## callees

- `0x18002fe60`
- `0x180030324`
- `0x180030710`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003037f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003037f`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800303af`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800303af`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030354`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030354`

## pseudocode

```c
__int64 __fastcall CreateScannerRequest(
        unsigned __int16 *a1,
        int a2,
        unsigned __int16 *a3,
        int a4,
        struct _SCANNER_REQUEST **a5)
{
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  int v11; // edi
  HANDLE v12; // rax

  *a5 = 0;
  v9 = LocalAlloc(0x40u, 0x28u);
  v10 = v9;
  if ( !v9 )
  {
LABEL_2:
    v11 = -1073741801;
    goto LABEL_9;
  }
  v9[1] = v9;
  *v9 = v9;
  if ( !a1
    || !(unsigned int)_o__wcsicmp(a1, L"*")
    || (v11 = LsaDbCopyString(a1, (unsigned __int16 **)v10 + 2), v11 >= 0) )
  {
    *((_DWORD *)v10 + 6) = a2;
    *((_DWORD *)v10 + 7) = a4;
    if ( !a3 || (v12 = OpenEventW(2u, 0, a3), (v10[4] = v12) != 0) )
    {
      *a5 = (struct _SCANNER_REQUEST *)v10;
      v10 = 0;
      v11 = 0;
      goto LABEL_9;
    }
    goto LABEL_2;
  }
LABEL_9:
  FreeScannerRequest(v10);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180030324  push    rbx
0x180030326  push    rbp
0x180030327  push    rsi
0x180030328  push    rdi
0x180030329  push    r14
0x18003032b  push    r15
0x18003032d  sub     rsp, 28h
0x180030331  mov     r14, [rsp+58h+arg_20]
0x180030339  mov     r15d, edx
0x18003033c  mov     edx, 28h ; '('; uBytes
0x180030341  mov     rdi, rcx
0x180030344  mov     ebp, r9d
0x180030347  mov     rsi, r8
0x18003034a  mov     qword ptr [r14], 0
0x180030351  lea     ecx, [rdx+18h]; uFlags
0x180030354  call    cs:__imp_LocalAlloc
0x18003035a  mov     rbx, rax
0x18003035d  test    rax, rax
0x180030360  jnz     short loc_180030369
0x180030362  mov     edi, 0C0000017h
0x180030367  jmp     short loc_1800303C5
0x180030369  mov     [rax+8], rbx
0x18003036d  mov     [rax], rbx
0x180030370  test    rdi, rdi
0x180030373  jz      short loc_18003039B
0x180030375  lea     rdx, asc_18003E5C8; "*"
0x18003037c  mov     rcx, rdi
0x18003037f  call    cs:__imp__o__wcsicmp
0x180030385  test    eax, eax
0x180030387  jz      short loc_18003039B
0x180030389  lea     rdx, [rbx+10h]; unsigned __int16 **
0x18003038d  mov     rcx, rdi; unsigned __int16 *
0x180030390  call    ?LsaDbCopyString@@YAJPEAGPEAPEAG@Z; LsaDbCopyString(ushort *,ushort * *)
0x180030395  mov     edi, eax
0x180030397  test    eax, eax
0x180030399  js      short loc_1800303C5
0x18003039b  mov     [rbx+18h], r15d
0x18003039f  mov     [rbx+1Ch], ebp
0x1800303a2  test    rsi, rsi
0x1800303a5  jz      short loc_1800303BE
0x1800303a7  xor     edx, edx; bInheritHandle
0x1800303a9  mov     r8, rsi; lpName
0x1800303ac  lea     ecx, [rdx+2]; dwDesiredAccess
0x1800303af  call    cs:__imp_OpenEventW
0x1800303b5  mov     [rbx+20h], rax
0x1800303b9  test    rax, rax
0x1800303bc  jz      short loc_180030362
0x1800303be  mov     [r14], rbx
0x1800303c1  xor     ebx, ebx
0x1800303c3  xor     edi, edi
0x1800303c5  mov     rcx, rbx; hMem
0x1800303c8  call    ?FreeScannerRequest@@YAXPEAU_SCANNER_REQUEST@@@Z; FreeScannerRequest(_SCANNER_REQUEST *)
0x1800303cd  mov     eax, edi
0x1800303cf  add     rsp, 28h
0x1800303d3  pop     r15
0x1800303d5  pop     r14
0x1800303d7  pop     rdi
0x1800303d8  pop     rsi
0x1800303d9  pop     rbp
0x1800303da  pop     rbx
0x1800303db  retn
```
