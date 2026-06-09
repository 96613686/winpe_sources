# CscUmFindOpenPattern

- ea: `0x180002820`
- end: `0x18000298b`
- name: `CscUmFindOpenPattern`
- size: `363`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001020`
- `0x1800016b0`

## callees

- `0x180002820`
- `0x1800029a0`
- `0x180002a40`
- `0x180002db0`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1800028ad`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1800028ad`
- `ntdll!RtlDuplicateUnicodeString` at `0x1800028f9`
- `ntdll!RtlDuplicateUnicodeString` at `0x1800028f9`

## pseudocode

```c
__int64 __fastcall CscUmFindOpenPattern(void ***a1, const UNICODE_STRING *a2, const UNICODE_STRING *a3)
{
  bool v3; // zf
  __int64 result; // rax
  const UNICODE_STRING *v7; // rbp
  struct _UNICODE_STRING *v8; // rax
  __int64 v9; // rdx
  void **v10; // rbx
  int ItemInformation; // edi
  int v12; // [rsp+30h] [rbp-78h]
  _QWORD v13[2]; // [rsp+40h] [rbp-68h] BYREF
  __int128 v14; // [rsp+50h] [rbp-58h]
  __int128 v15; // [rsp+60h] [rbp-48h]
  __int128 v16; // [rsp+70h] [rbp-38h]
  __int64 v17; // [rsp+80h] [rbp-28h]

  v13[0] = 393220;
  v3 = CscUmpLibraryState == 0;
  v17 = 0;
  *a1 = 0;
  v13[1] = L"\\\\";
  v14 = 0;
  v15 = 0;
  v16 = 0;
  if ( v3 )
    return 3221225860LL;
  v7 = (const UNICODE_STRING *)v13;
  if ( a2 )
    v7 = a2;
  v8 = (struct _UNICODE_STRING *)LocalAlloc(0, 0x30u);
  v10 = (void **)v8;
  if ( v8 )
  {
    *v8 = 0;
    v8[1] = 0;
    v8[2] = 0;
    *(_DWORD *)&v8->Length = 1130718291;
    LOBYTE(v8[2].Length) = 1;
    if ( !a3 || !a3->Length || (ItemInformation = RtlDuplicateUnicodeString(0, a3, v8 + 1), ItemInformation >= 0) )
    {
      ItemInformation = CscDriverOpenItemWithDispositionEx(v10 + 1, v9, v7, 6, 1048577, 7u, v12, 1);
      if ( ItemInformation >= 0 )
      {
        ItemInformation = CscDriverQueryItemInformation(v10[1]);
        if ( ItemInformation >= 0 )
        {
          if ( (v17 & 0x10) != 0 )
            goto LABEL_15;
          ItemInformation = -1073741565;
        }
      }
    }
    CscUmFindClose(v10);
    v10 = 0;
    goto LABEL_15;
  }
  ItemInformation = -1073741670;
LABEL_15:
  result = (unsigned int)ItemInformation;
  *a1 = v10;
  return result;
}

```

## disassembly

```asm
0x180002820  push    rsi
0x180002822  push    rdi
0x180002823  push    r15
0x180002825  sub     rsp, 90h
0x18000282c  xor     eax, eax
0x18000282e  mov     [rsp+0A8h+var_68], 60004h
0x180002837  cmp     cs:CscUmpLibraryState, 0
0x18000283e  xorps   xmm0, xmm0
0x180002841  mov     [rsp+0A8h+var_28], rax
0x180002849  mov     rdi, r8
0x18000284c  lea     rax, asc_18000B600; "\\\\"
0x180002853  mov     qword ptr [rcx], 0
0x18000285a  mov     [rsp+0A8h+var_60], rax
0x18000285f  mov     rsi, rcx
0x180002862  movups  [rsp+0A8h+var_58], xmm0
0x180002867  mov     r15d, 6
0x18000286d  movups  [rsp+0A8h+var_48], xmm0
0x180002872  movups  [rsp+0A8h+var_38], xmm0
0x180002877  jnz     short loc_18000288A
0x180002879  mov     eax, 0C0000184h
0x18000287e  add     rsp, 90h
0x180002885  pop     r15
0x180002887  pop     rdi
0x180002888  pop     rsi
0x180002889  retn
0x18000288a  test    rdx, rdx
0x18000288d  mov     [rsp+0A8h+arg_0], rbx
0x180002895  mov     [rsp+0A8h+arg_8], rbp
0x18000289d  lea     rbp, [rsp+0A8h+var_68]
0x1800028a2  cmovnz  rbp, rdx
0x1800028a6  mov     edx, 30h ; '0'; uBytes
0x1800028ab  xor     ecx, ecx; uFlags
0x1800028ad  call    cs:__imp_LocalAlloc
0x1800028b3  mov     rbx, rax
0x1800028b6  test    rax, rax
0x1800028b9  jnz     short loc_1800028C5
0x1800028bb  mov     edi, 0C000009Ah
0x1800028c0  jmp     loc_18000296A
0x1800028c5  mov     [rsp+0A8h+arg_10], r14
0x1800028cd  xorps   xmm0, xmm0
0x1800028d0  movups  xmmword ptr [rax], xmm0
0x1800028d3  movups  xmmword ptr [rax+10h], xmm0
0x1800028d7  movups  xmmword ptr [rax+20h], xmm0
0x1800028db  mov     dword ptr [rax], 43656453h
0x1800028e1  mov     byte ptr [rax+20h], 1
0x1800028e5  test    rdi, rdi
0x1800028e8  jz      short loc_180002905
0x1800028ea  cmp     word ptr [rdi], 0
0x1800028ee  jz      short loc_180002905
0x1800028f0  lea     r8, [rax+10h]; DestinationString
0x1800028f4  mov     rdx, rdi; SourceString
0x1800028f7  xor     ecx, ecx; Flags
0x1800028f9  call    cs:__imp_RtlDuplicateUnicodeString
0x1800028ff  mov     edi, eax
0x180002901  test    eax, eax
0x180002903  js      short loc_180002958
0x180002905  mov     [rsp+0A8h+var_70], 1; int
0x18000290d  lea     rcx, [rbx+8]; FileHandle
0x180002911  mov     [rsp+0A8h+var_80], 7; ULONG
0x180002919  mov     r9d, r15d
0x18000291c  mov     r8, rbp
0x18000291f  mov     [rsp+0A8h+var_88], 100001h; int
0x180002927  call    CscDriverOpenItemWithDispositionEx
0x18000292c  mov     edi, eax
0x18000292e  test    eax, eax
0x180002930  js      short loc_180002958
0x180002932  mov     rcx, [rbx+8]; FileHandle
0x180002936  lea     rdx, [rsp+0A8h+var_58]
0x18000293b  xor     r8d, r8d
0x18000293e  call    CscDriverQueryItemInformation
0x180002943  mov     edi, eax
0x180002945  test    eax, eax
0x180002947  js      short loc_180002958
0x180002949  test    byte ptr [rsp+0A8h+var_28], 10h
0x180002951  jnz     short loc_180002962
0x180002953  mov     edi, 0C0000103h
0x180002958  mov     rcx, rbx; hMem
0x18000295b  call    CscUmFindClose
0x180002960  xor     ebx, ebx
0x180002962  mov     r14, [rsp+0A8h+arg_10]
0x18000296a  mov     rbp, [rsp+0A8h+arg_8]
0x180002972  mov     eax, edi
0x180002974  mov     [rsi], rbx
0x180002977  mov     rbx, [rsp+0A8h+arg_0]
0x18000297f  add     rsp, 90h
0x180002986  pop     r15
0x180002988  pop     rdi
0x180002989  pop     rsi
0x18000298a  retn
```
