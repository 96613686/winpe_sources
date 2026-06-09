# DfsIsScopedServerName(ushort const *)

- ea: `0x1400591e4`
- end: `0x1400593bc`
- name: `?DfsIsScopedServerName@@YAEPEBG@Z`
- size: `472`
- prototype: `unsigned __int8 __fastcall(PCWSTR SourceString)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140010614`
- `0x140010b2c`
- `0x140011c54`
- `0x140021e40`
- `0x140059184`

## callees

- `0x14004a490`
- `0x1400582bc`
- `0x1400591e4`

## import_xrefs

- `ntdll!RtlOemStringToUnicodeString` at `0x140059327`
- `ntdll!RtlOemStringToUnicodeString` at `0x140059327`
- `ntdll!RtlFreeUnicodeString` at `0x140059364`
- `ntdll!RtlFreeUnicodeString` at `0x140059364`
- `ntdll!RtlCompareUnicodeString` at `0x140059345`
- `ntdll!RtlCompareUnicodeString` at `0x140059345`
- `ntdll!RtlInitUnicodeString` at `0x14005922e`
- `ntdll!RtlInitUnicodeString` at `0x14005922e`
- `ntdll!RtlInitUnicodeStringEx` at `0x140059241`
- `ntdll!RtlInitUnicodeStringEx` at `0x140059241`
- `netutils!NetApiBufferFree` at `0x140059395`
- `netutils!NetApiBufferFree` at `0x140059395`
- `srvcli!NetServerTransportEnum` at `0x1400592ae`
- `srvcli!NetServerTransportEnum` at `0x1400592ae`

## pseudocode

```c
char __fastcall DfsIsScopedServerName(PCWSTR SourceString)
{
  char v2; // di
  char v3; // si
  DWORD v4; // edx
  unsigned int v5; // ebx
  LPBYTE v6; // rcx
  __int64 v7; // r8
  USHORT v8; // ax
  UNICODE_STRING String1; // [rsp+40h] [rbp-40h] BYREF
  STRING SourceStringa; // [rsp+50h] [rbp-30h] BYREF
  UNICODE_STRING String2; // [rsp+60h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-10h] BYREF
  DWORD entriesread; // [rsp+B8h] [rbp+38h] BYREF
  DWORD totalentries; // [rsp+C0h] [rbp+40h] BYREF
  LPBYTE bufptr; // [rsp+C8h] [rbp+48h] BYREF

  bufptr = 0;
  entriesread = 0;
  totalentries = 0;
  v2 = 0;
  String1 = 0;
  v3 = 0;
  String2 = 0;
  DestinationString = 0;
  SourceStringa = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  if ( !RtlInitUnicodeStringEx(&String2, SourceString) )
  {
    if ( SourceString )
    {
      if ( *SourceString )
      {
        if ( !(unsigned int)DfsIsAdDomainName(&String2) )
        {
          DfsGetNetbiosName(&String2, &DestinationString, 0);
          if ( !NetServerTransportEnum(0, 2u, &bufptr, 0xFFFFFFFF, &entriesread, &totalentries, 0) )
          {
            v4 = entriesread;
            v5 = 0;
            if ( entriesread )
            {
              v6 = bufptr;
              while ( 1 )
              {
                v7 = 56LL * v5;
                if ( (v6[v7 + 48] & 4) != 0 )
                {
                  v8 = *(_WORD *)&v6[v7 + 24];
                  if ( (v6[v7 + 48] & 0x20) != 0 )
                  {
                    String1.MaximumLength = *(_WORD *)&v6[v7 + 24];
                    String1.Length = v8;
                    String1.Buffer = *(PWSTR *)&v6[v7 + 16];
                  }
                  else
                  {
                    SourceStringa.MaximumLength = *(_WORD *)&v6[v7 + 24];
                    SourceStringa.Length = v8;
                    SourceStringa.Buffer = *(PCHAR *)&v6[v7 + 16];
                    if ( RtlOemStringToUnicodeString(&String1, &SourceStringa, 1u) < 0 )
                      break;
                    v3 = 1;
                  }
                  if ( !RtlCompareUnicodeString(&String1, &DestinationString, 1u) )
                    v2 = 1;
                  if ( v3 )
                  {
                    RtlFreeUnicodeString(&String1);
                    v3 = 0;
                  }
                  if ( v2 )
                    break;
                  v6 = bufptr;
                  v4 = entriesread;
                }
                if ( ++v5 >= v4 )
                  goto LABEL_22;
              }
            }
          }
        }
      }
    }
  }
  v6 = bufptr;
LABEL_22:
  if ( v6 )
    NetApiBufferFree(v6);
  return v2;
}

```

## disassembly

```asm
0x1400591e4  mov     [rsp-28h+arg_0], rbx
0x1400591e9  push    rbp
0x1400591ea  push    rsi
0x1400591eb  push    rdi
0x1400591ec  push    r14
0x1400591ee  push    r15
0x1400591f0  mov     rbp, rsp
0x1400591f3  sub     rsp, 80h
0x1400591fa  xor     r14d, r14d
0x1400591fd  xorps   xmm0, xmm0
0x140059200  xorps   xmm1, xmm1
0x140059203  mov     [rbp+bufptr], r14
0x140059207  mov     rbx, rcx
0x14005920a  mov     [rbp+arg_8], r14d
0x14005920e  lea     rcx, [rbp+DestinationString]; DestinationString
0x140059212  mov     [rbp+arg_10], r14d
0x140059216  xor     edx, edx; SourceString
0x140059218  mov     dil, r14b
0x14005921b  movups  xmmword ptr [rbp+String1.Length], xmm0
0x14005921f  mov     sil, r14b
0x140059222  movups  xmmword ptr [rbp+String2.Length], xmm1
0x140059226  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14005922a  movups  xmmword ptr [rbp+SourceString.Length], xmm1
0x14005922e  call    cs:__imp_RtlInitUnicodeString
0x140059235  nop     dword ptr [rax+rax+00h]
0x14005923a  mov     rdx, rbx; SourceString
0x14005923d  lea     rcx, [rbp+String2]; DestinationString
0x140059241  call    cs:__imp_RtlInitUnicodeStringEx
0x140059248  nop     dword ptr [rax+rax+00h]
0x14005924d  test    eax, eax
0x14005924f  jnz     loc_14005938C
0x140059255  test    rbx, rbx
0x140059258  jz      loc_14005938C
0x14005925e  cmp     [rbx], r14w
0x140059262  jz      loc_14005938C
0x140059268  lea     rcx, [rbp+String2]; String2
0x14005926c  call    ?DfsIsAdDomainName@@YAHPEBU_UNICODE_STRING@@@Z; DfsIsAdDomainName(_UNICODE_STRING const *)
0x140059271  test    eax, eax
0x140059273  jnz     loc_14005938C
0x140059279  xor     r8d, r8d
0x14005927c  lea     rdx, [rbp+DestinationString]
0x140059280  lea     rcx, [rbp+String2]
0x140059284  call    DfsGetNetbiosName
0x140059289  lea     rax, [rbp+arg_10]
0x14005928d  mov     [rsp+80h+resume_handle], r14; resume_handle
0x140059292  mov     [rsp+80h+totalentries], rax; totalentries
0x140059297  lea     r8, [rbp+bufptr]; bufptr
0x14005929b  lea     rax, [rbp+arg_8]
0x14005929f  or      r9d, 0FFFFFFFFh; prefmaxlen
0x1400592a3  lea     edx, [r14+2]; level
0x1400592a7  mov     [rsp+80h+entriesread], rax; entriesread
0x1400592ac  xor     ecx, ecx; servername
0x1400592ae  call    cs:__imp_NetServerTransportEnum
0x1400592b5  nop     dword ptr [rax+rax+00h]
0x1400592ba  test    eax, eax
0x1400592bc  jnz     loc_14005938C
0x1400592c2  mov     edx, [rbp+arg_8]
0x1400592c5  mov     ebx, r14d
0x1400592c8  test    edx, edx
0x1400592ca  jz      loc_14005938C
0x1400592d0  mov     rcx, [rbp+bufptr]
0x1400592d4  lea     r15d, [r14+1]
0x1400592d8  mov     eax, ebx
0x1400592da  imul    r8, rax, 38h ; '8'
0x1400592de  test    byte ptr [r8+rcx+30h], 4
0x1400592e4  jz      loc_14005937F
0x1400592ea  test    byte ptr [r8+rcx+30h], 20h
0x1400592f0  movzx   eax, word ptr [r8+rcx+18h]
0x1400592f6  jz      short loc_14005930B
0x1400592f8  mov     [rbp+String1.MaximumLength], ax
0x1400592fc  mov     [rbp+String1.Length], ax
0x140059300  mov     rax, [r8+rcx+10h]
0x140059305  mov     [rbp+String1.Buffer], rax
0x140059309  jmp     short loc_14005933A
0x14005930b  mov     [rbp+SourceString.MaximumLength], ax
0x14005930f  lea     rdx, [rbp+SourceString]; SourceString
0x140059313  mov     [rbp+SourceString.Length], ax
0x140059317  mov     rax, [r8+rcx+10h]
0x14005931c  mov     r8b, r15b; AllocateDestinationString
0x14005931f  lea     rcx, [rbp+String1]; DestinationString
0x140059323  mov     [rbp+SourceString.Buffer], rax
0x140059327  call    cs:__imp_RtlOemStringToUnicodeString
0x14005932e  nop     dword ptr [rax+rax+00h]
0x140059333  test    eax, eax
0x140059335  js      short loc_14005938C
0x140059337  mov     sil, r15b
0x14005933a  mov     r8b, r15b; CaseInsensitive
0x14005933d  lea     rdx, [rbp+DestinationString]; String2
0x140059341  lea     rcx, [rbp+String1]; String1
0x140059345  call    cs:__imp_RtlCompareUnicodeString
0x14005934c  nop     dword ptr [rax+rax+00h]
0x140059351  test    eax, eax
0x140059353  movzx   edi, dil
0x140059357  cmovz   edi, r15d
0x14005935b  test    sil, sil
0x14005935e  jz      short loc_140059373
0x140059360  lea     rcx, [rbp+String1]; UnicodeString
0x140059364  call    cs:__imp_RtlFreeUnicodeString
0x14005936b  nop     dword ptr [rax+rax+00h]
0x140059370  mov     sil, r14b
0x140059373  test    dil, dil
0x140059376  jnz     short loc_14005938C
0x140059378  mov     rcx, [rbp+bufptr]
0x14005937c  mov     edx, [rbp+arg_8]
0x14005937f  add     ebx, r15d
0x140059382  cmp     ebx, edx
0x140059384  jb      loc_1400592D8
0x14005938a  jmp     short loc_140059390
0x14005938c  mov     rcx, [rbp+bufptr]; Buffer
0x140059390  test    rcx, rcx
0x140059393  jz      short loc_1400593A1
0x140059395  call    cs:__imp_NetApiBufferFree
0x14005939c  nop     dword ptr [rax+rax+00h]
0x1400593a1  mov     rbx, [rsp+80h+arg_0]
0x1400593a9  mov     al, dil
0x1400593ac  add     rsp, 80h
0x1400593b3  pop     r15
0x1400593b5  pop     r14
0x1400593b7  pop     rdi
0x1400593b8  pop     rsi
0x1400593b9  pop     rbp
0x1400593ba  retn
```
