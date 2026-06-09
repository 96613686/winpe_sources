# PrpConvertToMultiByte(ushort const *,ulong,ushort,char * *,ulong *,long *)

- ea: `0x180050410`
- end: `0x1800504d1`
- name: `?PrpConvertToMultiByte@@YAXPEBGKGPEAPEADPEAKPEAJ@Z`
- size: `193`
- prototype: `void __usercall(LPCWCH lpWideCharStr@<rcx>, unsigned int@<edx>, unsigned __int16@<r8w>, char **@<r9>, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002c284`

## callees

- `0x180050410`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180050479`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180050479`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005048f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005048f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800504ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800504ad`

## pseudocode

```c
void __fastcall PrpConvertToMultiByte(
        LPCWCH lpWideCharStr,
        unsigned int a2,
        unsigned __int16 a3,
        char **a4,
        unsigned int *a5,
        int *a6)
{
  CHAR *lpMultiByteStr; // rbx
  int v9; // ebp
  int cbMultiByte; // esi
  UINT v11; // r12d
  unsigned int v12; // eax
  char *v13; // rax

  *a4 = 0;
  *a6 = 0;
  *a5 = 0;
  if ( (a2 & 1) != 0 )
  {
    *a6 = -1073741596;
  }
  else
  {
    lpMultiByteStr = 0;
    v9 = a2 >> 1;
    cbMultiByte = 0;
    v11 = a3;
    while ( 1 )
    {
      v12 = WideCharToMultiByte(v11, 0, lpWideCharStr, v9, lpMultiByteStr, cbMultiByte, 0, 0);
      cbMultiByte = v12;
      if ( !v12 )
        break;
      if ( lpMultiByteStr )
        return;
      *a5 = v12;
      v13 = (char *)CoTaskMemAlloc(v12);
      *a4 = v13;
      lpMultiByteStr = v13;
      if ( !v13 )
      {
        *a6 = -1073741670;
        return;
      }
    }
    CoTaskMemFree(lpMultiByteStr);
    *a4 = 0;
    *a6 = -1073741470;
  }
}

```

## disassembly

```asm
0x180050410  push    rbx
0x180050412  push    rbp
0x180050413  push    rsi
0x180050414  push    rdi
0x180050415  push    r12
0x180050417  push    r13
0x180050419  push    r14
0x18005041b  push    r15
0x18005041d  sub     rsp, 48h
0x180050421  mov     rdi, [rsp+88h+arg_28]
0x180050429  mov     r13, rcx
0x18005042c  mov     r15, [rsp+88h+arg_20]
0x180050434  xor     ecx, ecx
0x180050436  mov     [r9], rcx
0x180050439  mov     r14, r9
0x18005043c  mov     ebp, edx
0x18005043e  mov     [rdi], ecx
0x180050440  mov     [r15], ecx
0x180050443  test    dl, 1
0x180050446  jz      short loc_180050450
0x180050448  mov     dword ptr [rdi], 0C00000E4h
0x18005044e  jmp     short loc_1800504C0
0x180050450  mov     rbx, rcx
0x180050453  shr     ebp, 1
0x180050455  mov     esi, ecx
0x180050457  movzx   r12d, r8w
0x18005045b  mov     [rsp+88h+lpUsedDefaultChar], rcx; lpUsedDefaultChar
0x180050460  mov     r9d, ebp; cchWideChar
0x180050463  mov     [rsp+88h+lpDefaultChar], rcx; lpDefaultChar
0x180050468  mov     r8, r13; lpWideCharStr
0x18005046b  mov     [rsp+88h+cbMultiByte], esi; cbMultiByte
0x18005046f  mov     ecx, r12d; CodePage
0x180050472  xor     edx, edx; dwFlags
0x180050474  mov     [rsp+88h+lpMultiByteStr], rbx; lpMultiByteStr
0x180050479  call    cs:__imp_WideCharToMultiByte
0x18005047f  mov     esi, eax
0x180050481  test    eax, eax
0x180050483  jz      short loc_1800504AA
0x180050485  test    rbx, rbx
0x180050488  jnz     short loc_1800504C0
0x18005048a  mov     ecx, esi; cb
0x18005048c  mov     [r15], esi
0x18005048f  call    cs:__imp_CoTaskMemAlloc
0x180050495  xor     ecx, ecx
0x180050497  mov     [r14], rax
0x18005049a  mov     rbx, rax
0x18005049d  test    rax, rax
0x1800504a0  jnz     short loc_18005045B
0x1800504a2  mov     dword ptr [rdi], 0C000009Ah
0x1800504a8  jmp     short loc_1800504C0
0x1800504aa  mov     rcx, rbx; pv
0x1800504ad  call    cs:__imp_CoTaskMemFree
0x1800504b3  mov     qword ptr [r14], 0
0x1800504ba  mov     dword ptr [rdi], 0C0000162h
0x1800504c0  add     rsp, 48h
0x1800504c4  pop     r15
0x1800504c6  pop     r14
0x1800504c8  pop     r13
0x1800504ca  pop     r12
0x1800504cc  pop     rdi
0x1800504cd  pop     rsi
0x1800504ce  pop     rbp
0x1800504cf  pop     rbx
0x1800504d0  retn
```
