# LsaDbpVerifyTrustLocation(_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *)

- ea: `0x18000cd2c`
- end: `0x18000cf26`
- name: `?LsaDbpVerifyTrustLocation@@YAJPEAU_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX@@@Z`
- size: `506`
- prototype: `__int64 __fastcall(struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000a2bc`
- `0x18000e9f0`

## callees

- `0x18000cd2c`
- `0x18000fd80`
- `0x180026674`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cef3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cefd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cf06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cef3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cefd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cf06`
- `ntdll!RtlEqualSid` at `0x18000cea5`
- `ntdll!RtlEqualSid` at `0x18000cec2`
- `ntdll!RtlEqualSid` at `0x18000cedc`
- `ntdll!RtlEqualSid` at `0x18000cea5`
- `ntdll!RtlEqualSid` at `0x18000cec2`
- `ntdll!RtlEqualSid` at `0x18000cedc`

## pseudocode

```c
__int64 __fastcall LsaDbpVerifyTrustLocation(struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdx
  void *v4; // rdi
  HLOCAL v5; // rsi
  int v7; // r15d
  int v8; // r12d
  int v9; // r14d
  int Match; // eax
  unsigned int v11; // ebx
  int v12; // eax
  __int64 v13; // r8
  int v14; // eax
  char v15; // cl
  char v16; // al
  BOOLEAN v17; // al
  int v18; // edx
  HLOCAL hMem; // [rsp+70h] [rbp+40h] BYREF
  void *v21; // [rsp+78h] [rbp+48h] BYREF
  PSID Sid1; // [rsp+80h] [rbp+50h] BYREF

  v3 = *((_QWORD *)a1 + 4);
  v4 = 0;
  v5 = 0;
  Sid1 = 0;
  v21 = 0;
  hMem = 0;
  v7 = 2;
  v8 = 1;
  v9 = 2;
  if ( v3 )
  {
    LOBYTE(a3) = 1;
    Match = LsaDbpForestTrustFindMatch(0, v3, a3, 0, &hMem);
    v5 = hMem;
    v11 = Match;
    if ( Match == -1073741198 )
    {
      v9 = 0;
    }
    else
    {
      if ( Match < 0 )
        goto LABEL_41;
      v9 = 1;
    }
  }
  LOBYTE(a3) = 1;
  v12 = LsaDbpForestTrustFindMatch(1, a1, a3, 0, &Sid1);
  v11 = v12;
  if ( v12 == -1073741198 )
  {
    v8 = 0;
    v11 = 0;
  }
  else if ( v12 < 0 )
  {
    goto LABEL_41;
  }
  if ( *((_QWORD *)a1 + 3) )
  {
    LOBYTE(v13) = 1;
    v14 = LsaDbpForestTrustFindMatch(1, (char *)a1 + 16, v13, 0, &v21);
    v4 = v21;
    v11 = v14;
    if ( v14 == -1073741198 )
    {
      v7 = 0;
      v11 = 0;
    }
    else
    {
      if ( v14 < 0 )
        goto LABEL_41;
      v7 = 1;
    }
  }
  if ( v9 == 1 || v8 == 1 || (v15 = 0, v7 == 1) )
    v15 = 1;
  if ( !v9 || !v8 || (v16 = 0, !v7) )
    v16 = 1;
  if ( v15 )
  {
    if ( v16 )
    {
      if ( v9 == 1 )
        v11 = -1073740775;
      else
        v11 = (v8 != 1) - 1073740774;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids,
          *((_QWORD *)a1 + 1));
      goto LABEL_41;
    }
    *((_DWORD *)a1 + 12) |= 0x20u;
  }
  if ( Sid1 && (v5 && !RtlEqualSid(Sid1, v5) || v4 && !RtlEqualSid(Sid1, v4)) )
  {
    v11 = -1073741811;
  }
  else if ( v5 && v4 )
  {
    v17 = RtlEqualSid(v5, v4);
    v18 = v11;
    if ( !v17 )
      v18 = -1073741811;
    v11 = v18;
  }
LABEL_41:
  LocalFree(v4);
  LocalFree(Sid1);
  LocalFree(v5);
  return v11;
}

```

## disassembly

```asm
0x18000cd2c  mov     [rsp-38h+arg_18], rbx
0x18000cd31  push    rbp
0x18000cd32  push    rsi
0x18000cd33  push    rdi
0x18000cd34  push    r12
0x18000cd36  push    r13
0x18000cd38  push    r14
0x18000cd3a  push    r15
0x18000cd3c  mov     rbp, rsp
0x18000cd3f  sub     rsp, 30h
0x18000cd43  mov     rdx, [rcx+20h]
0x18000cd47  xor     edi, edi
0x18000cd49  xor     esi, esi
0x18000cd4b  mov     [rbp+Sid1], 0
0x18000cd53  mov     [rbp+arg_8], rdi
0x18000cd57  mov     r13, rcx
0x18000cd5a  mov     [rbp+hMem], rsi
0x18000cd5e  lea     r15d, [rdi+2]
0x18000cd62  lea     r12d, [rdi+1]
0x18000cd66  mov     r14d, r15d
0x18000cd69  test    rdx, rdx
0x18000cd6c  jz      short loc_18000CDA1
0x18000cd6e  lea     rax, [rbp+hMem]
0x18000cd72  xor     r9d, r9d
0x18000cd75  mov     r8b, r12b
0x18000cd78  mov     [rsp+30h+var_10], rax
0x18000cd7d  xor     ecx, ecx
0x18000cd7f  call    ?LsaDbpForestTrustFindMatch@@YAJW4LSA_ROUTING_MATCH_TYPE@@PEAXEPEAU_UNICODE_STRING@@PEAPEAX@Z; LsaDbpForestTrustFindMatch(LSA_ROUTING_MATCH_TYPE,void *,uchar,_UNICODE_STRING *,void * *)
0x18000cd84  mov     rsi, [rbp+hMem]
0x18000cd88  mov     ebx, eax
0x18000cd8a  cmp     eax, 0C0000272h
0x18000cd8f  jnz     short loc_18000CD96
0x18000cd91  xor     r14d, r14d
0x18000cd94  jmp     short loc_18000CDA1
0x18000cd96  test    eax, eax
0x18000cd98  js      loc_18000CEF0
0x18000cd9e  mov     r14d, r12d
0x18000cda1  lea     rax, [rbp+Sid1]
0x18000cda5  xor     r9d, r9d
0x18000cda8  mov     r8b, r12b
0x18000cdab  mov     [rsp+30h+var_10], rax
0x18000cdb0  mov     rdx, r13
0x18000cdb3  mov     ecx, r12d
0x18000cdb6  call    ?LsaDbpForestTrustFindMatch@@YAJW4LSA_ROUTING_MATCH_TYPE@@PEAXEPEAU_UNICODE_STRING@@PEAPEAX@Z; LsaDbpForestTrustFindMatch(LSA_ROUTING_MATCH_TYPE,void *,uchar,_UNICODE_STRING *,void * *)
0x18000cdbb  mov     ebx, eax
0x18000cdbd  cmp     eax, 0C0000272h
0x18000cdc2  jnz     short loc_18000CDCB
0x18000cdc4  xor     r12d, r12d
0x18000cdc7  xor     ebx, ebx
0x18000cdc9  jmp     short loc_18000CDD3
0x18000cdcb  test    eax, eax
0x18000cdcd  js      loc_18000CEF0
0x18000cdd3  lea     rdx, [r13+10h]
0x18000cdd7  cmp     [rdx+8], rdi
0x18000cddb  jz      short loc_18000CE17
0x18000cddd  xor     r9d, r9d
0x18000cde0  lea     rax, [rbp+arg_8]
0x18000cde4  mov     r8b, 1
0x18000cde7  mov     [rsp+30h+var_10], rax
0x18000cdec  lea     ecx, [r9+1]
0x18000cdf0  call    ?LsaDbpForestTrustFindMatch@@YAJW4LSA_ROUTING_MATCH_TYPE@@PEAXEPEAU_UNICODE_STRING@@PEAPEAX@Z; LsaDbpForestTrustFindMatch(LSA_ROUTING_MATCH_TYPE,void *,uchar,_UNICODE_STRING *,void * *)
0x18000cdf5  mov     rdi, [rbp+arg_8]
0x18000cdf9  mov     ebx, eax
0x18000cdfb  cmp     eax, 0C0000272h
0x18000ce00  jnz     short loc_18000CE09
0x18000ce02  xor     r15d, r15d
0x18000ce05  xor     ebx, ebx
0x18000ce07  jmp     short loc_18000CE17
0x18000ce09  test    eax, eax
0x18000ce0b  js      loc_18000CEF0
0x18000ce11  mov     r15d, 1
0x18000ce17  cmp     r14d, 1
0x18000ce1b  jz      short loc_18000CE2B
0x18000ce1d  cmp     r12d, 1
0x18000ce21  jz      short loc_18000CE2B
0x18000ce23  xor     cl, cl
0x18000ce25  cmp     r15d, 1
0x18000ce29  jnz     short loc_18000CE2D
0x18000ce2b  mov     cl, 1
0x18000ce2d  test    r14d, r14d
0x18000ce30  jz      short loc_18000CE3E
0x18000ce32  test    r12d, r12d
0x18000ce35  jz      short loc_18000CE3E
0x18000ce37  xor     al, al
0x18000ce39  test    r15d, r15d
0x18000ce3c  jnz     short loc_18000CE40
0x18000ce3e  mov     al, 1
0x18000ce40  test    cl, cl
0x18000ce42  jz      short loc_18000CE94
0x18000ce44  test    al, al
0x18000ce46  jz      short loc_18000CE8F
0x18000ce48  cmp     r14d, 1
0x18000ce4c  jnz     short loc_18000CE55
0x18000ce4e  mov     ebx, 0C0000419h
0x18000ce53  jmp     short loc_18000CE64
0x18000ce55  xor     ebx, ebx
0x18000ce57  cmp     r12d, 1
0x18000ce5b  setnz   bl
0x18000ce5e  add     ebx, 0C000041Ah
0x18000ce64  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce6b  test    dword ptr [rcx+1Ch], 100h
0x18000ce72  jz      short loc_18000CEF0
0x18000ce74  mov     r9, [r13+8]
0x18000ce78  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x18000ce7f  mov     rcx, [rcx+10h]
0x18000ce83  mov     edx, 0Ah
0x18000ce88  call    WPP_SF_S
0x18000ce8d  jmp     short loc_18000CEF0
0x18000ce8f  or      dword ptr [r13+30h], 20h
0x18000ce94  mov     rcx, [rbp+Sid1]; Sid1
0x18000ce98  test    rcx, rcx
0x18000ce9b  jz      short loc_18000CECC
0x18000ce9d  test    rsi, rsi
0x18000cea0  jz      short loc_18000CEB6
0x18000cea2  mov     rdx, rsi; Sid2
0x18000cea5  call    cs:__imp_RtlEqualSid
0x18000ceab  test    al, al
0x18000cead  jnz     short loc_18000CEB6
0x18000ceaf  mov     ebx, 0C000000Dh
0x18000ceb4  jmp     short loc_18000CEF0
0x18000ceb6  test    rdi, rdi
0x18000ceb9  jz      short loc_18000CECC
0x18000cebb  mov     rcx, [rbp+Sid1]; Sid1
0x18000cebf  mov     rdx, rdi; Sid2
0x18000cec2  call    cs:__imp_RtlEqualSid
0x18000cec8  test    al, al
0x18000ceca  jz      short loc_18000CEAF
0x18000cecc  test    rsi, rsi
0x18000cecf  jz      short loc_18000CEF0
0x18000ced1  test    rdi, rdi
0x18000ced4  jz      short loc_18000CEF0
0x18000ced6  mov     rdx, rdi; Sid2
0x18000ced9  mov     rcx, rsi; Sid1
0x18000cedc  call    cs:__imp_RtlEqualSid
0x18000cee2  mov     edx, ebx
0x18000cee4  mov     ebx, 0C000000Dh
0x18000cee9  test    al, al
0x18000ceeb  cmovz   edx, ebx
0x18000ceee  mov     ebx, edx
0x18000cef0  mov     rcx, rdi; hMem
0x18000cef3  call    cs:__imp_LocalFree
0x18000cef9  mov     rcx, [rbp+Sid1]; hMem
0x18000cefd  call    cs:__imp_LocalFree
0x18000cf03  mov     rcx, rsi; hMem
0x18000cf06  call    cs:__imp_LocalFree
0x18000cf0c  mov     eax, ebx
0x18000cf0e  mov     rbx, [rsp+30h+arg_18]
0x18000cf16  add     rsp, 30h
0x18000cf1a  pop     r15
0x18000cf1c  pop     r14
0x18000cf1e  pop     r13
0x18000cf20  pop     r12
0x18000cf22  pop     rdi
0x18000cf23  pop     rsi
0x18000cf24  pop     rbp
0x18000cf25  retn
```
