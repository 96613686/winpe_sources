# SetKeyContainerSecurity(unsigned __int64)

- ea: `0x18002ba00`
- end: `0x18002bcf8`
- name: `?SetKeyContainerSecurity@@YAJ_K@Z`
- size: `760`
- prototype: `__int64 __fastcall(HCRYPTPROV hProv)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001c3ec`
- `0x18002aaa8`

## callees

- `0x1800049ac`
- `0x18001722c`
- `0x1800216f0`
- `0x18002ba00`

## import_xrefs

- `msvcrt!free` at `0x18002ba5b`
- `msvcrt!free` at `0x18002baef`
- `msvcrt!free` at `0x18002baf9`
- `msvcrt!free` at `0x18002bb68`
- `msvcrt!free` at `0x18002bb72`
- `msvcrt!free` at `0x18002bbd4`
- `msvcrt!free` at `0x18002bbde`
- `msvcrt!free` at `0x18002bc44`
- `msvcrt!free` at `0x18002bc4e`
- `msvcrt!free` at `0x18002bcb7`
- `msvcrt!free` at `0x18002bcc1`
- `msvcrt!free` at `0x18002bcd0`
- `msvcrt!free` at `0x18002bcda`
- `msvcrt!free` at `0x18002ba5b`
- `msvcrt!free` at `0x18002baef`
- `msvcrt!free` at `0x18002baf9`
- `msvcrt!free` at `0x18002bb68`
- `msvcrt!free` at `0x18002bb72`
- `msvcrt!free` at `0x18002bbd4`
- `msvcrt!free` at `0x18002bbde`
- `msvcrt!free` at `0x18002bc44`
- `msvcrt!free` at `0x18002bc4e`
- `msvcrt!free` at `0x18002bcb7`
- `msvcrt!free` at `0x18002bcc1`
- `msvcrt!free` at `0x18002bcd0`
- `msvcrt!free` at `0x18002bcda`
- `ADVAPI32!CryptSetProvParam` at `0x18002bc6c`
- `ADVAPI32!CryptSetProvParam` at `0x18002bc6c`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18002ba30`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18002ba30`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18002bbf9`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18002bbf9`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002bb1d`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002bb89`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002bb1d`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002bb89`
- `ADVAPI32!InitializeAcl` at `0x18002baa4`
- `ADVAPI32!InitializeAcl` at `0x18002baa4`
- `ADVAPI32!GetLengthSid` at `0x18002ba71`
- `ADVAPI32!GetLengthSid` at `0x18002ba7c`
- `ADVAPI32!GetLengthSid` at `0x18002ba71`
- `ADVAPI32!GetLengthSid` at `0x18002ba7c`
- `KERNEL32!GetLastError` at `0x18002baae`
- `KERNEL32!GetLastError` at `0x18002bb27`
- `KERNEL32!GetLastError` at `0x18002bb93`
- `KERNEL32!GetLastError` at `0x18002bc03`
- `KERNEL32!GetLastError` at `0x18002bc76`
- `KERNEL32!GetLastError` at `0x18002baae`
- `KERNEL32!GetLastError` at `0x18002bb27`
- `KERNEL32!GetLastError` at `0x18002bb93`
- `KERNEL32!GetLastError` at `0x18002bc03`
- `KERNEL32!GetLastError` at `0x18002bc76`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SetKeyContainerSecurity(HCRYPTPROV hProv)
{
  PSID v2; // rbp
  int v3; // ebx
  void *v5; // rsi
  DWORD LengthSid; // ebx
  DWORD v7; // edi
  struct _ACL *v8; // rbx
  DWORD LastError; // eax
  DWORD v10; // eax
  DWORD v11; // eax
  DWORD v12; // eax
  DWORD v13; // eax
  _OWORD pSecurityDescriptor[2]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v15; // [rsp+40h] [rbp-28h]
  void *Block; // [rsp+78h] [rbp+10h] BYREF
  struct _ACL *v17; // [rsp+80h] [rbp+18h]

  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v15 = 0;
  InitializeSecurityDescriptor(pSecurityDescriptor, 1u);
  v2 = g_pAdminSid;
  Block = 0;
  v3 = MQSec_CalculateServiceSid(&Block);
  if ( v3 < 0 )
  {
    free(Block);
    return (unsigned int)v3;
  }
  v5 = Block;
  LengthSid = GetLengthSid(Block);
  v7 = LengthSid + GetLengthSid(v2) + 28;
  v8 = (struct _ACL *)MmAllocate(v7);
  v17 = v8;
  if ( !InitializeAcl(v8, v7, 2u) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 10, WPP_7ba6051e75cf378a980396cdbbb4b879_Traceguids, LastError);
LABEL_7:
    free(v8);
    free(v5);
    return 3222143084LL;
  }
  if ( !AddAccessAllowedAce(v8, 2u, 0xF003Fu, v2) )
  {
    v10 = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 11, WPP_7ba6051e75cf378a980396cdbbb4b879_Traceguids, v10);
    goto LABEL_7;
  }
  if ( !AddAccessAllowedAce(v8, 2u, 0xF003Fu, v5) )
  {
    v11 = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 12, WPP_7ba6051e75cf378a980396cdbbb4b879_Traceguids, v11);
    goto LABEL_7;
  }
  if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v8, 0) )
  {
    v12 = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 13, WPP_7ba6051e75cf378a980396cdbbb4b879_Traceguids, v12);
    goto LABEL_7;
  }
  if ( !CryptSetProvParam(hProv, 8u, (const BYTE *)pSecurityDescriptor, 4u) )
  {
    v13 = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 14, WPP_7ba6051e75cf378a980396cdbbb4b879_Traceguids, v13);
    goto LABEL_7;
  }
  free(v8);
  free(v5);
  return 0;
}

```

## disassembly

```asm
0x18002ba00  mov     r11, rsp
0x18002ba03  mov     [r11+8], rbx
0x18002ba07  mov     [r11+20h], rbp
0x18002ba0b  push    rsi
0x18002ba0c  push    rdi
0x18002ba0d  push    r14
0x18002ba0f  sub     rsp, 50h
0x18002ba13  mov     r14, rcx
0x18002ba16  xorps   xmm0, xmm0
0x18002ba19  xor     eax, eax
0x18002ba1b  movups  [rsp+68h+pSecurityDescriptor], xmm0
0x18002ba20  movups  [rsp+68h+var_38], xmm0
0x18002ba25  mov     [r11-28h], rax
0x18002ba29  lea     edx, [rax+1]; dwRevision
0x18002ba2c  lea     rcx, [r11-48h]; pSecurityDescriptor
0x18002ba30  call    cs:__imp_InitializeSecurityDescriptor
0x18002ba36  mov     rbp, cs:?g_pAdminSid@@3PEAXEA; void * g_pAdminSid
0x18002ba3d  mov     [rsp+68h+Block], 0
0x18002ba46  lea     rcx, [rsp+68h+Block]; void **
0x18002ba4b  call    ?MQSec_CalculateServiceSid@@YAJPEAPEAX@Z; MQSec_CalculateServiceSid(void * *)
0x18002ba50  mov     ebx, eax
0x18002ba52  test    eax, eax
0x18002ba54  jns     short loc_18002BA69
0x18002ba56  mov     rcx, [rsp+68h+Block]; Block
0x18002ba5b  call    cs:__imp_free
0x18002ba61  nop
0x18002ba62  mov     eax, ebx
0x18002ba64  jmp     loc_18002BCE3
0x18002ba69  mov     rsi, [rsp+68h+Block]
0x18002ba6e  mov     rcx, rsi; pSid
0x18002ba71  call    cs:__imp_GetLengthSid
0x18002ba77  mov     ebx, eax
0x18002ba79  mov     rcx, rbp; pSid
0x18002ba7c  call    cs:__imp_GetLengthSid
0x18002ba82  lea     edi, [rax+1Ch]
0x18002ba85  add     edi, ebx
0x18002ba87  mov     ecx, edi; unsigned __int64
0x18002ba89  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18002ba8e  mov     rbx, rax
0x18002ba91  mov     [rsp+68h+arg_10], rax
0x18002ba99  mov     r8d, 2; dwAclRevision
0x18002ba9f  mov     edx, edi; nAclLength
0x18002baa1  mov     rcx, rax; pAcl
0x18002baa4  call    cs:__imp_InitializeAcl
0x18002baaa  test    eax, eax
0x18002baac  jnz     short loc_18002BB0A
0x18002baae  call    cs:__imp_GetLastError
0x18002bab4  lea     rdx, WPP_GLOBAL_Control
0x18002babb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bac2  cmp     rcx, rdx
0x18002bac5  jz      short loc_18002BAEC
0x18002bac7  test    byte ptr [rcx+10Ch], 1
0x18002bace  jz      short loc_18002BAEC
0x18002bad0  mov     edx, 0Ah
0x18002bad5  mov     r9d, eax
0x18002bad8  lea     r8, WPP_7ba6051e75cf378a980396cdbbb4b879_Traceguids
0x18002badf  mov     rcx, [rcx+100h]
0x18002bae6  call    WPP_SF_d
0x18002baeb  nop
0x18002baec  mov     rcx, rbx; Block
0x18002baef  call    cs:__imp_free
0x18002baf5  nop
0x18002baf6  mov     rcx, rsi; Block
0x18002baf9  call    cs:__imp_free
0x18002baff  nop
0x18002bb00  mov     eax, 0C00E006Ch
0x18002bb05  jmp     loc_18002BCE3
0x18002bb0a  mov     r9, rbp; pSid
0x18002bb0d  mov     edi, 0F003Fh
0x18002bb12  mov     r8d, edi; AccessMask
0x18002bb15  mov     edx, 2; dwAceRevision
0x18002bb1a  mov     rcx, rbx; pAcl
0x18002bb1d  call    cs:__imp_AddAccessAllowedAce
0x18002bb23  test    eax, eax
0x18002bb25  jnz     short loc_18002BB7B
0x18002bb27  call    cs:__imp_GetLastError
0x18002bb2d  lea     rdx, WPP_GLOBAL_Control
0x18002bb34  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bb3b  cmp     rcx, rdx
0x18002bb3e  jz      short loc_18002BB65
0x18002bb40  test    byte ptr [rcx+10Ch], 1
0x18002bb47  jz      short loc_18002BB65
0x18002bb49  mov     edx, 0Bh
0x18002bb4e  mov     r9d, eax
0x18002bb51  lea     r8, WPP_7ba6051e75cf378a980396cdbbb4b879_Traceguids
0x18002bb58  mov     rcx, [rcx+100h]
0x18002bb5f  call    WPP_SF_d
0x18002bb64  nop
0x18002bb65  mov     rcx, rbx; Block
0x18002bb68  call    cs:__imp_free
0x18002bb6e  nop
0x18002bb6f  mov     rcx, rsi; Block
0x18002bb72  call    cs:__imp_free
0x18002bb78  nop
0x18002bb79  jmp     short loc_18002BB00
0x18002bb7b  mov     r9, rsi; pSid
0x18002bb7e  mov     r8d, edi; AccessMask
0x18002bb81  mov     edx, 2; dwAceRevision
0x18002bb86  mov     rcx, rbx; pAcl
0x18002bb89  call    cs:__imp_AddAccessAllowedAce
0x18002bb8f  test    eax, eax
0x18002bb91  jnz     short loc_18002BBEA
0x18002bb93  call    cs:__imp_GetLastError
0x18002bb99  lea     rdx, WPP_GLOBAL_Control
0x18002bba0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bba7  cmp     rcx, rdx
0x18002bbaa  jz      short loc_18002BBD1
0x18002bbac  test    byte ptr [rcx+10Ch], 1
0x18002bbb3  jz      short loc_18002BBD1
0x18002bbb5  mov     edx, 0Ch
0x18002bbba  mov     r9d, eax
0x18002bbbd  lea     r8, WPP_7ba6051e75cf378a980396cdbbb4b879_Traceguids
0x18002bbc4  mov     rcx, [rcx+100h]
0x18002bbcb  call    WPP_SF_d
0x18002bbd0  nop
0x18002bbd1  mov     rcx, rbx; Block
0x18002bbd4  call    cs:__imp_free
0x18002bbda  nop
0x18002bbdb  mov     rcx, rsi; Block
0x18002bbde  call    cs:__imp_free
0x18002bbe4  nop
0x18002bbe5  jmp     loc_18002BB00
0x18002bbea  xor     r9d, r9d; bDaclDefaulted
0x18002bbed  mov     r8, rbx; pDacl
0x18002bbf0  lea     edx, [r9+1]; bDaclPresent
0x18002bbf4  lea     rcx, [rsp+68h+pSecurityDescriptor]; pSecurityDescriptor
0x18002bbf9  call    cs:__imp_SetSecurityDescriptorDacl
0x18002bbff  test    eax, eax
0x18002bc01  jnz     short loc_18002BC5A
0x18002bc03  call    cs:__imp_GetLastError
0x18002bc09  lea     rdx, WPP_GLOBAL_Control
0x18002bc10  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bc17  cmp     rcx, rdx
0x18002bc1a  jz      short loc_18002BC41
0x18002bc1c  test    byte ptr [rcx+10Ch], 1
0x18002bc23  jz      short loc_18002BC41
0x18002bc25  mov     edx, 0Dh
0x18002bc2a  mov     r9d, eax
0x18002bc2d  lea     r8, WPP_7ba6051e75cf378a980396cdbbb4b879_Traceguids
0x18002bc34  mov     rcx, [rcx+100h]
0x18002bc3b  call    WPP_SF_d
0x18002bc40  nop
0x18002bc41  mov     rcx, rbx; Block
0x18002bc44  call    cs:__imp_free
0x18002bc4a  nop
0x18002bc4b  mov     rcx, rsi; Block
0x18002bc4e  call    cs:__imp_free
0x18002bc54  nop
0x18002bc55  jmp     loc_18002BB00
0x18002bc5a  mov     r9d, 4; dwFlags
0x18002bc60  lea     r8, [rsp+68h+pSecurityDescriptor]; pbData
0x18002bc65  lea     edx, [r9+4]; dwParam
0x18002bc69  mov     rcx, r14; hProv
0x18002bc6c  call    cs:__imp_CryptSetProvParam
0x18002bc72  test    eax, eax
0x18002bc74  jnz     short loc_18002BCCD
0x18002bc76  call    cs:__imp_GetLastError
0x18002bc7c  lea     rdx, WPP_GLOBAL_Control
0x18002bc83  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bc8a  cmp     rcx, rdx
0x18002bc8d  jz      short loc_18002BCB4
0x18002bc8f  test    byte ptr [rcx+10Ch], 1
0x18002bc96  jz      short loc_18002BCB4
0x18002bc98  mov     edx, 0Eh
0x18002bc9d  mov     r9d, eax
0x18002bca0  lea     r8, WPP_7ba6051e75cf378a980396cdbbb4b879_Traceguids
0x18002bca7  mov     rcx, [rcx+100h]
0x18002bcae  call    WPP_SF_d
0x18002bcb3  nop
0x18002bcb4  mov     rcx, rbx; Block
0x18002bcb7  call    cs:__imp_free
0x18002bcbd  nop
0x18002bcbe  mov     rcx, rsi; Block
0x18002bcc1  call    cs:__imp_free
0x18002bcc7  nop
0x18002bcc8  jmp     loc_18002BB00
0x18002bccd  mov     rcx, rbx; Block
0x18002bcd0  call    cs:__imp_free
0x18002bcd6  nop
0x18002bcd7  mov     rcx, rsi; Block
0x18002bcda  call    cs:__imp_free
0x18002bce0  nop
0x18002bce1  xor     eax, eax
0x18002bce3  lea     r11, [rsp+68h+var_18]
0x18002bce8  mov     rbx, [r11+20h]
0x18002bcec  mov     rbp, [r11+38h]
0x18002bcf0  mov     rsp, r11
0x18002bcf3  pop     r14
0x18002bcf5  pop     rdi
0x18002bcf6  pop     rsi
0x18002bcf7  retn
```
