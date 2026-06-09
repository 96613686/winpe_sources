# CClient::SetSecret(tagVARIANT)

- ea: `0x1800075bc`
- end: `0x18000767e`
- name: `?SetSecret@CClient@@AEAAHUtagVARIANT@@@Z`
- size: `194`
- prototype: `__int64 __fastcall(CClient *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004c70`

## callees

- `0x1800075bc`
- `0x1800094e4`
- `0x18001d31c`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x1800075fd`
- `KERNEL32!WideCharToMultiByte` at `0x1800075fd`

## string_xrefs

- `0x180007629`: `Unable to convert client shared secret to multi-byte string during Client processing`

## pseudocode

```c
__int64 __fastcall CClient::SetSecret(CClient *this, struct tagVARIANT *a2)
{
  char *v2; // rsi
  __int64 v4; // rbx

  v2 = (char *)this + 104;
  v4 = -1;
  if ( WideCharToMultiByte(0, 0, a2->bstrVal, -1, (LPSTR)this + 104, 255, 0, 0) )
  {
    do
      ++v4;
    while ( v2[v4] );
    *((_DWORD *)this + 346) = v4;
    return 1;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Unable to convert client shared secret to multi-byte string during Client processing");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_1d3eb203fb0232ec74f11b7ccc17ee04_Traceguids, "NPSRAD");
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1800075bc  mov     rax, rsp
0x1800075bf  mov     [rax+8], rbx
0x1800075c3  mov     [rax+10h], rsi
0x1800075c7  push    rdi
0x1800075c8  sub     rsp, 40h
0x1800075cc  mov     r8, [rdx+8]; lpWideCharStr
0x1800075d0  lea     rsi, [rcx+68h]
0x1800075d4  mov     qword ptr [rax-10h], 0
0x1800075dc  mov     rdi, rcx
0x1800075df  mov     qword ptr [rax-18h], 0
0x1800075e7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800075eb  mov     dword ptr [rax-20h], 0FFh
0x1800075f2  mov     r9d, ebx; cchWideChar
0x1800075f5  xor     edx, edx; dwFlags
0x1800075f7  mov     [rax-28h], rsi
0x1800075fb  xor     ecx, ecx; CodePage
0x1800075fd  call    cs:__imp_WideCharToMultiByte
0x180007603  test    eax, eax
0x180007605  jnz     short loc_18000765A
0x180007607  mov     rax, cs:WPP_GLOBAL_Control
0x18000760e  lea     rcx, WPP_GLOBAL_Control
0x180007615  cmp     rax, rcx
0x180007618  jz      short loc_180007656
0x18000761a  cmp     byte ptr [rax+19h], 2
0x18000761e  jb      short loc_180007656
0x180007620  test    dword ptr [rax+1Ch], 100h
0x180007627  jz      short loc_180007656
0x180007629  lea     rcx, aUnableToConver_0; "Unable to convert client shared secret "...
0x180007630  call    WppDbgPrint
0x180007635  mov     rcx, cs:WPP_GLOBAL_Control
0x18000763c  lea     edx, [rbx+16h]
0x18000763f  lea     r9, aNpsrad; "NPSRAD"
0x180007646  lea     r8, WPP_1d3eb203fb0232ec74f11b7ccc17ee04_Traceguids
0x18000764d  mov     rcx, [rcx+10h]
0x180007651  call    WPP_SF_s
0x180007656  xor     eax, eax
0x180007658  jmp     short loc_18000766E
0x18000765a  inc     rbx
0x18000765d  cmp     byte ptr [rsi+rbx], 0
0x180007661  jnz     short loc_18000765A
0x180007663  mov     [rdi+568h], ebx
0x180007669  mov     eax, 1
0x18000766e  mov     rbx, [rsp+48h+arg_0]
0x180007673  mov     rsi, [rsp+48h+arg_8]
0x180007678  add     rsp, 40h
0x18000767c  pop     rdi
0x18000767d  retn
```
