# CreateSIDAcl(_ACL *,_ACL * *,void *,ulong,ulong)

- ea: `0x1800321a0`
- end: `0x1800322d4`
- name: `?CreateSIDAcl@@YAKPEAU_ACL@@PEAPEAU1@PEAXKK@Z`
- size: `308`
- prototype: `unsigned int __usercall@<eax>(PACL pAcl@<rcx>, struct _ACL **@<rdx>, void *@<r8>, unsigned int@<r9d>, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800306b0`
- `0x180065938`
- `0x180065a60`

## callees

- `0x1800321a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032203`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032203`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800322c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800322c9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800321e0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800321e0`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18003228b`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18003228b`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800322b3`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800322b3`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180032255`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180032255`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800321f9`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800321f9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800321c5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800321c5`

## pseudocode

```c
__int64 __fastcall CreateSIDAcl(PACL pAcl, struct _ACL **a2, void *a3, DWORD a4, DWORD AceFlags)
{
  DWORD LengthSid; // eax
  int AclSize; // ecx
  DWORD v11; // ebx
  struct _ACL *v12; // rax
  struct _ACL *v13; // rsi
  DWORD LastError; // ebx
  WORD i; // bp
  LPVOID pAce; // [rsp+60h] [rbp+8h] BYREF

  LengthSid = GetLengthSid(a3);
  if ( pAcl )
    AclSize = pAcl->AclSize;
  else
    AclSize = 8;
  v11 = AclSize + LengthSid + 12;
  v12 = (struct _ACL *)LocalAlloc(0, v11);
  v13 = v12;
  if ( v12 )
  {
    if ( InitializeAcl(v12, v11, 4u) && AddAccessAllowedAceEx(v13, 4u, AceFlags, a4, a3) )
    {
      LastError = 0;
      if ( pAcl && pAcl->AceCount )
      {
        for ( i = 0; i < pAcl->AceCount; ++i )
        {
          pAce = 0;
          if ( !GetAce(pAcl, i, &pAce) || !AddAce(v13, 4u, i + 1, pAce, *((unsigned __int16 *)pAce + 1)) )
            goto LABEL_5;
        }
      }
    }
    else
    {
LABEL_5:
      LastError = GetLastError();
      if ( LastError )
      {
        LocalFree(v13);
        return LastError;
      }
    }
    *a2 = v13;
  }
  else
  {
    return 14;
  }
  return LastError;
}

```

## disassembly

```asm
0x1800321a0  mov     [rsp+arg_8], rbx
0x1800321a5  mov     [rsp+arg_10], rbp
0x1800321aa  push    rsi
0x1800321ab  push    rdi
0x1800321ac  push    r12
0x1800321ae  push    r14
0x1800321b0  push    r15
0x1800321b2  sub     rsp, 30h
0x1800321b6  mov     rdi, rcx
0x1800321b9  mov     r14d, r9d
0x1800321bc  mov     rcx, r8; pSid
0x1800321bf  mov     rbp, r8
0x1800321c2  mov     r15, rdx
0x1800321c5  call    cs:__imp_GetLengthSid
0x1800321cb  xor     r12d, r12d
0x1800321ce  test    rdi, rdi
0x1800321d1  jz      short loc_18003222F
0x1800321d3  movzx   ecx, word ptr [rdi+2]
0x1800321d7  lea     ebx, [rax+0Ch]
0x1800321da  add     ebx, ecx
0x1800321dc  xor     ecx, ecx; uFlags
0x1800321de  mov     edx, ebx; uBytes
0x1800321e0  call    cs:__imp_LocalAlloc
0x1800321e6  mov     rsi, rax
0x1800321e9  test    rax, rax
0x1800321ec  jz      short loc_180032236
0x1800321ee  mov     r8d, 4; dwAclRevision
0x1800321f4  mov     edx, ebx; nAclLength
0x1800321f6  mov     rcx, rax; pAcl
0x1800321f9  call    cs:__imp_InitializeAcl
0x1800321ff  test    eax, eax
0x180032201  jnz     short loc_18003223D
0x180032203  call    cs:__imp_GetLastError
0x180032209  mov     ebx, eax
0x18003220b  test    eax, eax
0x18003220d  jnz     loc_1800322C6
0x180032213  mov     [r15], rsi
0x180032216  mov     rbp, [rsp+58h+arg_10]
0x18003221b  mov     eax, ebx
0x18003221d  mov     rbx, [rsp+58h+arg_8]
0x180032222  add     rsp, 30h
0x180032226  pop     r15
0x180032228  pop     r14
0x18003222a  pop     r12
0x18003222c  pop     rdi
0x18003222d  pop     rsi
0x18003222e  retn
0x18003222f  mov     ecx, 8
0x180032234  jmp     short loc_1800321D7
0x180032236  mov     ebx, 0Eh
0x18003223b  jmp     short loc_180032216
0x18003223d  mov     r8d, [rsp+58h+AceFlags]; AceFlags
0x180032245  mov     r9d, r14d; AccessMask
0x180032248  mov     edx, 4; dwAceRevision
0x18003224d  mov     [rsp+58h+pSid], rbp; pSid
0x180032252  mov     rcx, rsi; pAcl
0x180032255  call    cs:__imp_AddAccessAllowedAceEx
0x18003225b  test    eax, eax
0x18003225d  jz      short loc_180032203
0x18003225f  mov     ebx, r12d
0x180032262  test    rdi, rdi
0x180032265  jz      short loc_180032213
0x180032267  cmp     [rdi+4], r12w
0x18003226c  jz      short loc_180032213
0x18003226e  mov     ebp, r12d
0x180032271  cmp     bp, [rdi+4]
0x180032275  jnb     short loc_180032213
0x180032277  movzx   r14d, bp
0x18003227b  lea     r8, [rsp+58h+pAce]; pAce
0x180032280  mov     edx, r14d; dwAceIndex
0x180032283  mov     [rsp+58h+pAce], r12
0x180032288  mov     rcx, rdi; pAcl
0x18003228b  call    cs:__imp_GetAce
0x180032291  test    eax, eax
0x180032293  jz      loc_180032203
0x180032299  mov     r9, [rsp+58h+pAce]; pAceList
0x18003229e  lea     r8d, [r14+1]; dwStartingAceIndex
0x1800322a2  mov     edx, 4; dwAceRevision
0x1800322a7  mov     rcx, rsi; pAcl
0x1800322aa  movzx   eax, word ptr [r9+2]
0x1800322af  mov     dword ptr [rsp+58h+pSid], eax; nAceListLength
0x1800322b3  call    cs:__imp_AddAce
0x1800322b9  test    eax, eax
0x1800322bb  jz      loc_180032203
0x1800322c1  inc     bp
0x1800322c4  jmp     short loc_180032271
0x1800322c6  mov     rcx, rsi; hMem
0x1800322c9  call    cs:__imp_LocalFree
0x1800322cf  jmp     loc_180032216
```
