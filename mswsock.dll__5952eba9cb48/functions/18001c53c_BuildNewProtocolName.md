# BuildNewProtocolName

- ea: `0x18001c53c`
- end: `0x18001c6a4`
- name: `BuildNewProtocolName`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180030cdc`

## callees

- `0x1800119a0`
- `0x18001c53c`
- `0x180021408`
- `0x1800222f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18001c571`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18001c571`

## pseudocode

```c
__int64 __fastcall BuildNewProtocolName(__int64 a1, __int64 a2, wchar_t *a3)
{
  int v6; // ebx
  __int64 result; // rax
  const wchar_t *v8; // r8
  wchar_t pszDest[16]; // [rsp+40h] [rbp-48h] BYREF

  if ( (unsigned int)_o__wcsnicmp(*(_QWORD *)(a2 + 32), L"\\device\\", 8) )
  {
    StringCbPrintfW(a3, 0x200u, L"MSAFD %s [%s]", a1, *(_QWORD *)(a2 + 32));
    goto LABEL_11;
  }
  v6 = *(_DWORD *)(a2 + 20);
  if ( v6 == 0x80000000 )
  {
    v6 = 0;
  }
  else if ( v6 < 0 )
  {
    v6 = -v6;
  }
  switch ( *(_DWORD *)(a2 + 16) )
  {
    case 1:
      v8 = L"STREAM";
      goto LABEL_19;
    case 2:
      v8 = L"DATAGRAM";
      goto LABEL_19;
    case 3:
      v8 = L"RAW";
      goto LABEL_19;
    case 4:
      v8 = L"RDM";
      goto LABEL_19;
    case 5:
      v8 = L"SEQPACKET";
LABEL_19:
      StringCbCopyW(pszDest, 0x20u, v8);
      goto LABEL_10;
  }
  StringCbPrintfW(pszDest, 0x20u, L"%d");
LABEL_10:
  StringCbPrintfW(a3, 0x200u, L"MSAFD %s [%s] %s %d", a1, *(_QWORD *)(a2 + 32), pszDest, v6);
LABEL_11:
  result = 0;
  a3[255] = 0;
  return result;
}

```

## disassembly

```asm
0x18001c53c  mov     [rsp+arg_18], rbx
0x18001c541  push    rbp
0x18001c542  push    rsi
0x18001c543  push    rdi
0x18001c544  sub     rsp, 70h
0x18001c548  mov     rax, cs:__security_cookie
0x18001c54f  xor     rax, rsp
0x18001c552  mov     [rsp+88h+var_28], rax
0x18001c557  mov     rdi, rdx
0x18001c55a  mov     rsi, r8
0x18001c55d  mov     rbp, rcx
0x18001c560  lea     rdx, aDevice; "\\device\\"
0x18001c567  mov     r8d, 8
0x18001c56d  mov     rcx, [rdi+20h]
0x18001c571  call    cs:__imp__o__wcsnicmp
0x18001c578  nop     dword ptr [rax+rax+00h]
0x18001c57d  test    eax, eax
0x18001c57f  jnz     loc_18001C67F
0x18001c585  mov     ebx, [rdi+14h]
0x18001c588  cmp     ebx, 80000000h
0x18001c58e  jnz     loc_18001C631
0x18001c594  xor     ebx, ebx
0x18001c596  mov     r9d, [rdi+10h]
0x18001c59a  mov     ecx, r9d
0x18001c59d  sub     ecx, 1
0x18001c5a0  jz      loc_18001C664
0x18001c5a6  sub     ecx, 1
0x18001c5a9  jz      loc_18001C65B
0x18001c5af  sub     ecx, 1
0x18001c5b2  jz      loc_18001C652
0x18001c5b8  sub     ecx, 1
0x18001c5bb  jz      loc_18001C649
0x18001c5c1  cmp     ecx, 1
0x18001c5c4  mov     edx, 20h ; ' '; cbDest
0x18001c5c9  lea     rcx, [rsp+88h+pszDest]; pszDest
0x18001c5ce  jz      short loc_18001C640
0x18001c5d0  lea     r8, aD; "%d"
0x18001c5d7  call    StringCbPrintfW
0x18001c5dc  lea     rax, [rsp+88h+pszDest]
0x18001c5e1  mov     [rsp+88h+var_58], ebx
0x18001c5e5  mov     [rsp+88h+var_60], rax
0x18001c5ea  lea     r8, aMsafdSSSD; "MSAFD %s [%s] %s %d"
0x18001c5f1  mov     rax, [rdi+20h]
0x18001c5f5  mov     r9, rbp
0x18001c5f8  mov     edx, 200h; cbDest
0x18001c5fd  mov     [rsp+88h+var_68], rax
0x18001c602  mov     rcx, rsi; pszDest
0x18001c605  call    StringCbPrintfW
0x18001c60a  xor     eax, eax
0x18001c60c  mov     [rsi+1FEh], ax
0x18001c613  mov     rcx, [rsp+88h+var_28]
0x18001c618  xor     rcx, rsp; StackCookie
0x18001c61b  call    __security_check_cookie
0x18001c620  mov     rbx, [rsp+88h+arg_18]
0x18001c628  add     rsp, 70h
0x18001c62c  pop     rdi
0x18001c62d  pop     rsi
0x18001c62e  pop     rbp
0x18001c62f  retn
0x18001c631  test    ebx, ebx
0x18001c633  jns     loc_18001C596
0x18001c639  neg     ebx
0x18001c63b  jmp     loc_18001C596
0x18001c640  lea     r8, aSeqpacket; "SEQPACKET"
0x18001c647  jmp     short loc_18001C675
0x18001c649  lea     r8, aRdm; "RDM"
0x18001c650  jmp     short loc_18001C66B
0x18001c652  lea     r8, aRaw; "RAW"
0x18001c659  jmp     short loc_18001C66B
0x18001c65b  lea     r8, aDatagram; "DATAGRAM"
0x18001c662  jmp     short loc_18001C66B
0x18001c664  lea     r8, aStream; "STREAM"
0x18001c66b  lea     rcx, [rsp+88h+pszDest]; pszDest
0x18001c670  mov     edx, 20h ; ' '; cbDest
0x18001c675  call    StringCbCopyW
0x18001c67a  jmp     loc_18001C5DC
0x18001c67f  mov     rax, [rdi+20h]
0x18001c683  lea     r8, aMsafdSS; "MSAFD %s [%s]"
0x18001c68a  mov     r9, rbp
0x18001c68d  mov     [rsp+88h+var_68], rax
0x18001c692  mov     edx, 200h; cbDest
0x18001c697  mov     rcx, rsi; pszDest
0x18001c69a  call    StringCbPrintfW
0x18001c69f  jmp     loc_18001C60A
```
