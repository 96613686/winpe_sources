# NcaRpcAPIsInitSecurityMode(ulong)

- ea: `0x18001af58`
- end: `0x18001b00a`
- name: `?NcaRpcAPIsInitSecurityMode@@YAJK@Z`
- size: `178`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b060`

## callees

- `0x180004f34`
- `0x18001af58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001afb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001afb1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001af9d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001af9d`

## pseudocode

```c
__int64 __fastcall NcaRpcAPIsInitSecurityMode(unsigned int a1)
{
  unsigned int v1; // ebx
  __int64 v2; // rdi
  __int64 v3; // rcx
  wchar_t **v4; // rsi
  __int64 *v5; // r14
  signed int LastError; // eax

  v1 = 0;
  v2 = 0;
  v3 = 3LL * a1;
  v4 = &off_180028120[v3];
  v5 = &qword_1800295D8[v3];
  while ( (unsigned int)v2 < 2 )
  {
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v4[v2], 1u, (PSECURITY_DESCRIPTOR *)&v5[v2], 0) )
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_f7ee278a5b20347feecbcc0df5ae90c8_Traceguids, v1);
      return v1;
    }
    v2 = (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x18001af58  push    rbx
0x18001af5a  push    rsi
0x18001af5b  push    rdi
0x18001af5c  push    r14
0x18001af5e  sub     rsp, 28h
0x18001af62  mov     eax, ecx
0x18001af64  xor     ebx, ebx
0x18001af66  xor     edi, edi
0x18001af68  lea     rcx, [rax+rax*2]
0x18001af6c  lea     rax, cs:180000000h
0x18001af73  lea     rsi, rva off_180028120[rax]; "O:SYG:SYD:(A;;RCWD;;;BA)(A;;RCWD;;;NO)("... ...
0x18001af7a  lea     r14, rva qword_1800295D8[rax]
0x18001af81  lea     rsi, [rsi+rcx*8]
0x18001af85  lea     r14, [r14+rcx*8]
0x18001af89  cmp     edi, 2
0x18001af8c  jnb     short loc_18001AFFD
0x18001af8e  mov     rcx, [rsi+rdi*8]; StringSecurityDescriptor
0x18001af92  lea     r8, [r14+rdi*8]; SecurityDescriptor
0x18001af96  xor     r9d, r9d; SecurityDescriptorSize
0x18001af99  lea     edx, [r9+1]; StringSDRevision
0x18001af9d  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001afa4  nop     dword ptr [rax+rax+00h]
0x18001afa9  test    eax, eax
0x18001afab  jz      short loc_18001AFB1
0x18001afad  inc     edi
0x18001afaf  jmp     short loc_18001AF89
0x18001afb1  call    cs:__imp_GetLastError
0x18001afb8  nop     dword ptr [rax+rax+00h]
0x18001afbd  mov     ebx, eax
0x18001afbf  test    eax, eax
0x18001afc1  jle     short loc_18001AFCC
0x18001afc3  movzx   ebx, ax
0x18001afc6  or      ebx, 80070000h
0x18001afcc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001afd3  lea     rax, WPP_GLOBAL_Control
0x18001afda  cmp     rcx, rax
0x18001afdd  jz      short loc_18001AFFD
0x18001afdf  test    byte ptr [rcx+1Ch], 1
0x18001afe3  jz      short loc_18001AFFD
0x18001afe5  mov     rcx, [rcx+10h]
0x18001afe9  lea     r8, WPP_f7ee278a5b20347feecbcc0df5ae90c8_Traceguids
0x18001aff0  mov     edx, 0Bh
0x18001aff5  mov     r9d, ebx
0x18001aff8  call    WPP_SF_d
0x18001affd  mov     eax, ebx
0x18001afff  add     rsp, 28h
0x18001b003  pop     r14
0x18001b005  pop     rdi
0x18001b006  pop     rsi
0x18001b007  pop     rbx
0x18001b008  retn
```
