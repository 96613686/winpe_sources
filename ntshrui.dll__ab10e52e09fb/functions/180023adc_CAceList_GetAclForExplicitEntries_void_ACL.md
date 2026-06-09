# CAceList::GetAclForExplicitEntries(void *,_ACL * *)

- ea: `0x180023adc`
- end: `0x180023ca2`
- name: `?GetAclForExplicitEntries@CAceList@@QEAAJPEAXPEAPEAU_ACL@@@Z`
- size: `454`
- prototype: `__int64 __fastcall(CAceList *__hidden this, void *, struct _ACL **)`
- caller_count: `7`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180055420`
- `0x180056420`
- `0x180059a80`
- `0x18005bcac`
- `0x18005be58`
- `0x18005bf4c`
- `0x18006e0c4`

## callees

- `0x18000f720`
- `0x180023adc`
- `0x180023ca8`
- `0x180055284`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x180023b81`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x180023be7`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x180023b81`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x180023be7`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180023b47`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180023b47`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023b2a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023b2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023c88`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023c88`

## pseudocode

```c
__int64 __fastcall CAceList::GetAclForExplicitEntries(CAceList *this, void *a2, struct _ACL **a3)
{
  int v5; // edi
  int RequiredExplictAclSize; // ebp
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  DWORD v11; // ebp
  struct _ACL *v12; // rax
  struct _ACL *v13; // rbx
  INT_PTR i; // rbp
  struct _DPA *v15; // rcx
  unsigned __int8 *Ptr; // rax
  INT_PTR v17; // rbp
  struct _DPA *v18; // rcx
  PVOID v19; // rax
  INT_PTR j; // rbp
  struct _DPA *v21; // rcx
  struct CAce *v22; // rax
  INT_PTR v23; // rbp
  struct _DPA *v24; // rcx
  struct CAce *v25; // rax

  v5 = -2147024882;
  RequiredExplictAclSize = CAceList::_GetRequiredExplictAclSize(this, a2, this);
  v11 = CAceList::_GetRequiredExplictAclSize(v8, v7, (char *)this + 8) + RequiredExplictAclSize + 8;
  if ( !*((_QWORD *)this + 3) )
    v11 += CAceList::_GetRequiredExplictAclSize(v10, v9, (char *)this + 16);
  v12 = (struct _ACL *)LocalAlloc(0x40u, v11);
  v13 = v12;
  if ( !v12 )
    goto LABEL_33;
  InitializeAcl(v12, v11, 2u);
  for ( i = 0; ; ++i )
  {
    v15 = *(struct _DPA **)this;
    v5 = 0;
    if ( !*(_QWORD *)this || i >= *(int *)v15 )
      break;
    Ptr = (unsigned __int8 *)DPA_GetPtr(v15, i);
    if ( !AddAccessDeniedAceEx(v13, 2u, Ptr[1], *((_DWORD *)Ptr + 1), *((PSID *)Ptr + 1)) )
    {
      v5 = -2147024882;
      break;
    }
  }
  if ( !*((_DWORD *)this + 6) && !*((_DWORD *)this + 7) )
  {
    v17 = 0;
    if ( v5 >= 0 )
    {
      while ( 1 )
      {
        v18 = (struct _DPA *)*((_QWORD *)this + 2);
        if ( !v18 || v17 >= *(int *)v18 )
          break;
        v19 = DPA_GetPtr(v18, v17);
        if ( (*((_BYTE *)v19 + 28) & 1) == 0
          && !AddAccessDeniedAceEx(v13, 2u, *((_BYTE *)v19 + 1) & 0xEF, *((_DWORD *)v19 + 1), *((PSID *)v19 + 1)) )
        {
          v5 = -2147024882;
          goto LABEL_23;
        }
        ++v17;
      }
    }
  }
  for ( j = 0; v5 >= 0; v5 = CAceList::_AddAllowedAceToAcl(this, v22, 0, v13) )
  {
    v21 = (struct _DPA *)*((_QWORD *)this + 1);
    if ( !v21 )
      break;
    if ( j >= *(int *)v21 )
      break;
    v22 = (struct CAce *)DPA_GetPtr(v21, j++);
  }
LABEL_23:
  if ( *((_DWORD *)this + 6) || *((_DWORD *)this + 7) )
  {
LABEL_31:
    if ( v5 >= 0 )
      goto LABEL_33;
LABEL_32:
    LocalFree(v13);
    v13 = 0;
    goto LABEL_33;
  }
  v23 = 0;
  if ( v5 < 0 )
    goto LABEL_32;
  while ( 1 )
  {
    v24 = (struct _DPA *)*((_QWORD *)this + 2);
    if ( !v24 )
      break;
    if ( v23 < *(int *)v24 )
    {
      v25 = (struct CAce *)DPA_GetPtr(v24, v23);
      if ( (*((_BYTE *)v25 + 28) & 1) != 0 )
        v5 = CAceList::_AddAllowedAceToAcl(this, v25, 1, v13);
      ++v23;
      if ( v5 >= 0 )
        continue;
    }
    goto LABEL_31;
  }
LABEL_33:
  *a3 = v13;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180023adc  push    rbx
0x180023ade  push    rbp
0x180023adf  push    rsi
0x180023ae0  push    rdi
0x180023ae1  push    r14
0x180023ae3  push    r15
0x180023ae5  sub     rsp, 38h
0x180023ae9  mov     r15, r8
0x180023aec  mov     rsi, rcx
0x180023aef  mov     r8, rcx
0x180023af2  mov     edi, 8007000Eh
0x180023af7  call    ?_GetRequiredExplictAclSize@CAceList@@AEAAKPEAXAEAV?$CDPA@VCAce@@V?$CTContainer_PolicyUnOwned@VCAce@@@@@@@Z; CAceList::_GetRequiredExplictAclSize(void *,CDPA<CAce,CTContainer_PolicyUnOwned<CAce>> &)
0x180023afc  lea     r8, [rsi+8]
0x180023b00  mov     ebp, eax
0x180023b02  call    ?_GetRequiredExplictAclSize@CAceList@@AEAAKPEAXAEAV?$CDPA@VCAce@@V?$CTContainer_PolicyUnOwned@VCAce@@@@@@@Z; CAceList::_GetRequiredExplictAclSize(void *,CDPA<CAce,CTContainer_PolicyUnOwned<CAce>> &)
0x180023b07  add     ebp, 8
0x180023b0a  add     ebp, eax
0x180023b0c  cmp     dword ptr [rsi+18h], 0
0x180023b10  jnz     short loc_180023B23
0x180023b12  cmp     dword ptr [rsi+1Ch], 0
0x180023b16  jnz     short loc_180023B23
0x180023b18  lea     r8, [rsi+10h]
0x180023b1c  call    ?_GetRequiredExplictAclSize@CAceList@@AEAAKPEAXAEAV?$CDPA@VCAce@@V?$CTContainer_PolicyUnOwned@VCAce@@@@@@@Z; CAceList::_GetRequiredExplictAclSize(void *,CDPA<CAce,CTContainer_PolicyUnOwned<CAce>> &)
0x180023b21  add     ebp, eax
0x180023b23  mov     edx, ebp; uBytes
0x180023b25  mov     ecx, 40h ; '@'; uFlags
0x180023b2a  call    cs:__imp_LocalAlloc
0x180023b30  mov     rbx, rax
0x180023b33  test    rax, rax
0x180023b36  jz      loc_180023C90
0x180023b3c  mov     r8d, 2; dwAclRevision
0x180023b42  mov     edx, ebp; nAclLength
0x180023b44  mov     rcx, rax; pAcl
0x180023b47  call    cs:__imp_InitializeAcl
0x180023b4d  xor     ebp, ebp
0x180023b4f  mov     rcx, [rsi]; hdpa
0x180023b52  xor     edi, edi
0x180023b54  test    rcx, rcx
0x180023b57  jz      short loc_180023B95
0x180023b59  movsxd  rax, dword ptr [rcx]
0x180023b5c  cmp     rbp, rax
0x180023b5f  jge     short loc_180023B95
0x180023b61  mov     rdx, rbp; i
0x180023b64  call    DPA_GetPtr
0x180023b69  lea     edx, [rdi+2]; dwAceRevision
0x180023b6c  mov     rcx, rbx; pAcl
0x180023b6f  mov     r9d, [rax+4]; AccessMask
0x180023b73  movzx   r8d, byte ptr [rax+1]; AceFlags
0x180023b78  mov     rax, [rax+8]
0x180023b7c  mov     [rsp+68h+pSid], rax; pSid
0x180023b81  call    cs:__imp_AddAccessDeniedAceEx
0x180023b87  test    eax, eax
0x180023b89  jz      short loc_180023B90
0x180023b8b  inc     rbp
0x180023b8e  jmp     short loc_180023B4F
0x180023b90  mov     edi, 8007000Eh
0x180023b95  cmp     dword ptr [rsi+18h], 0
0x180023b99  jnz     short loc_180023BFD
0x180023b9b  cmp     dword ptr [rsi+1Ch], 0
0x180023b9f  jnz     short loc_180023BFD
0x180023ba1  xor     ebp, ebp
0x180023ba3  test    edi, edi
0x180023ba5  js      short loc_180023BFD
0x180023ba7  mov     rcx, [rsi+10h]; hdpa
0x180023bab  test    rcx, rcx
0x180023bae  jz      short loc_180023BFD
0x180023bb0  movsxd  rax, dword ptr [rcx]
0x180023bb3  cmp     rbp, rax
0x180023bb6  jge     short loc_180023BFD
0x180023bb8  mov     rdx, rbp; i
0x180023bbb  call    DPA_GetPtr
0x180023bc0  mov     r9, rax
0x180023bc3  test    byte ptr [rax+1Ch], 1
0x180023bc7  jnz     short loc_180023BF1
0x180023bc9  movzx   r8d, byte ptr [rax+1]
0x180023bce  mov     edx, 2; dwAceRevision
0x180023bd3  mov     rax, [rax+8]
0x180023bd7  and     r8d, 0FFFFFFEFh; AceFlags
0x180023bdb  mov     r9d, [r9+4]; AccessMask
0x180023bdf  mov     rcx, rbx; pAcl
0x180023be2  mov     [rsp+68h+pSid], rax; pSid
0x180023be7  call    cs:__imp_AddAccessDeniedAceEx
0x180023bed  test    eax, eax
0x180023bef  jz      short loc_180023BF6
0x180023bf1  inc     rbp
0x180023bf4  jmp     short loc_180023BA7
0x180023bf6  mov     edi, 8007000Eh
0x180023bfb  jmp     short loc_180023C36
0x180023bfd  xor     ebp, ebp
0x180023bff  test    edi, edi
0x180023c01  js      short loc_180023C36
0x180023c03  mov     rcx, [rsi+8]; hdpa
0x180023c07  test    rcx, rcx
0x180023c0a  jz      short loc_180023C36
0x180023c0c  movsxd  rax, dword ptr [rcx]
0x180023c0f  cmp     rbp, rax
0x180023c12  jge     short loc_180023C36
0x180023c14  mov     rdx, rbp; i
0x180023c17  call    DPA_GetPtr
0x180023c1c  mov     r9, rbx; struct _ACL *
0x180023c1f  xor     r8d, r8d; bool
0x180023c22  mov     rdx, rax; struct CAce *
0x180023c25  mov     rcx, rsi; this
0x180023c28  call    ?_AddAllowedAceToAcl@CAceList@@AEAAJQEAVCAce@@_NPEAU_ACL@@@Z; CAceList::_AddAllowedAceToAcl(CAce * const,bool,_ACL *)
0x180023c2d  inc     rbp
0x180023c30  mov     edi, eax
0x180023c32  test    eax, eax
0x180023c34  jns     short loc_180023C03
0x180023c36  cmp     dword ptr [rsi+18h], 0
0x180023c3a  jnz     short loc_180023C81
0x180023c3c  cmp     dword ptr [rsi+1Ch], 0
0x180023c40  jnz     short loc_180023C81
0x180023c42  xor     ebp, ebp
0x180023c44  test    edi, edi
0x180023c46  js      short loc_180023C85
0x180023c48  mov     rcx, [rsi+10h]; hdpa
0x180023c4c  test    rcx, rcx
0x180023c4f  jz      short loc_180023C90
0x180023c51  movsxd  rax, dword ptr [rcx]
0x180023c54  cmp     rbp, rax
0x180023c57  jge     short loc_180023C81
0x180023c59  mov     rdx, rbp; i
0x180023c5c  call    DPA_GetPtr
0x180023c61  test    byte ptr [rax+1Ch], 1
0x180023c65  jz      short loc_180023C7A
0x180023c67  mov     r9, rbx; struct _ACL *
0x180023c6a  mov     r8b, 1; bool
0x180023c6d  mov     rdx, rax; struct CAce *
0x180023c70  mov     rcx, rsi; this
0x180023c73  call    ?_AddAllowedAceToAcl@CAceList@@AEAAJQEAVCAce@@_NPEAU_ACL@@@Z; CAceList::_AddAllowedAceToAcl(CAce * const,bool,_ACL *)
0x180023c78  mov     edi, eax
0x180023c7a  inc     rbp
0x180023c7d  test    edi, edi
0x180023c7f  jns     short loc_180023C48
0x180023c81  test    edi, edi
0x180023c83  jns     short loc_180023C90
0x180023c85  mov     rcx, rbx; hMem
0x180023c88  call    cs:__imp_LocalFree
0x180023c8e  xor     ebx, ebx
0x180023c90  mov     [r15], rbx
0x180023c93  mov     eax, edi
0x180023c95  add     rsp, 38h
0x180023c99  pop     r15
0x180023c9b  pop     r14
0x180023c9d  pop     rdi
0x180023c9e  pop     rsi
0x180023c9f  pop     rbp
0x180023ca0  pop     rbx
0x180023ca1  retn
```
