# DiscpBuildTunnelPolicyTemplate

- ea: `0x180014b74`
- end: `0x180014d75`
- name: `DiscpBuildTunnelPolicyTemplate`
- size: `513`
- prototype: `__int64 __fastcall(__int64, int *, unsigned int, STRSAFE_LPWSTR *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180014e84`

## callees

- `0x180001cfe`
- `0x18000bdb0`
- `0x180014b74`
- `0x180015890`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x180014bad`
- `ISCSIUM!DiscpAllocMemory` at `0x180014bad`
- `WS2_32!__imp_htonl` at `0x180014d23`
- `WS2_32!__imp_htonl` at `0x180014d30`
- `WS2_32!__imp_htonl` at `0x180014d23`
- `WS2_32!__imp_htonl` at `0x180014d30`
- `WS2_32!__imp_htons` at `0x180014c1a`
- `WS2_32!__imp_htons` at `0x180014c28`
- `WS2_32!__imp_htons` at `0x180014c36`
- `WS2_32!__imp_htons` at `0x180014c44`
- `WS2_32!__imp_htons` at `0x180014c51`
- `WS2_32!__imp_htons` at `0x180014c5e`
- `WS2_32!__imp_htons` at `0x180014c6b`
- `WS2_32!__imp_htons` at `0x180014c80`
- `WS2_32!__imp_htons` at `0x180014c1a`
- `WS2_32!__imp_htons` at `0x180014c28`
- `WS2_32!__imp_htons` at `0x180014c36`
- `WS2_32!__imp_htons` at `0x180014c44`
- `WS2_32!__imp_htons` at `0x180014c51`
- `WS2_32!__imp_htons` at `0x180014c5e`
- `WS2_32!__imp_htons` at `0x180014c6b`
- `WS2_32!__imp_htons` at `0x180014c80`

## pseudocode

```c
__int64 __fastcall DiscpBuildTunnelPolicyTemplate(__int64 a1, int *a2, unsigned int a3, STRSAFE_LPWSTR *a4, _QWORD *a5)
{
  int v5; // esi
  __int64 v6; // rbp
  int *v8; // rbx
  char *v9; // rax
  char *v10; // r13
  char *v11; // rdi
  u_long *v12; // r14
  __int64 v13; // rdx
  int v14; // r12d
  int v15; // r15d
  int v16; // r14d
  int v17; // ebp
  int v18; // esi
  int v19; // edi
  int v20; // ebx
  u_short v21; // ax
  __int64 result; // rax
  int v23; // [rsp+60h] [rbp-58h]
  u_long *v24; // [rsp+68h] [rbp-50h]

  v5 = *a2;
  v6 = a1;
  v23 = *a2;
  v8 = a2;
  v9 = (char *)DiscpAllocMemory(308);
  v10 = v9;
  if ( !v9 )
    return 8;
  memset_0(v9, 0, 0x134u);
  v11 = v10 + 72;
  *a4 = (STRSAFE_LPWSTR)(v10 + 156);
  v12 = (u_long *)(v8 + 1);
  v24 = (u_long *)(v8 + 1);
  if ( v5 )
  {
    v14 = htons(*((_WORD *)v8 + 13));
    v15 = htons(*((_WORD *)v8 + 12));
    v16 = htons(*((_WORD *)v8 + 11));
    v17 = htons(*((_WORD *)v8 + 10));
    v18 = htons(*((_WORD *)v8 + 9));
    v19 = htons(*((_WORD *)v8 + 8));
    v20 = htons(*((_WORD *)v8 + 7));
    v21 = htons(*((_WORD *)a2 + 6));
    StringCchPrintfW(
      *a4,
      0x4Cu,
      L"iSCSI_Tunnel_POLICY_to_%04x:%04x:%04x:%04x:%04x:%04x:%04x:%04x",
      v21,
      v20,
      v19,
      v18,
      v17,
      v16,
      v15,
      v14);
    v12 = v24;
    v11 = v10 + 72;
    v8 = a2;
    v5 = v23;
    v6 = a1;
  }
  else
  {
    StringCchPrintfW(
      (STRSAFE_LPWSTR)v10 + 78,
      0x4Cu,
      L"iSCSI_Tunnel_POLICY_to_%d.%d.%d.%d",
      *(unsigned __int8 *)v12,
      *((unsigned __int8 *)v8 + 5),
      *((unsigned __int8 *)v8 + 6),
      *((unsigned __int8 *)v8 + 7));
  }
  result = DiscpFillIpsecProposals(v11, v13, a3);
  if ( !(_DWORD)result )
  {
    *(_DWORD *)v10 = 0;
    *((_QWORD *)v10 + 1) = v11;
    *((_DWORD *)v10 + 1) = 3;
    *((_DWORD *)v10 + 4) = v5 != 0;
    *((_DWORD *)v10 + 13) = 360;
    *((_DWORD *)v10 + 14) = 360;
    if ( v5 )
    {
      *(_OWORD *)(v10 + 20) = *(_OWORD *)(v6 + 12);
      *(_OWORD *)(v10 + 36) = *(_OWORD *)(v8 + 3);
    }
    else
    {
      *((_DWORD *)v10 + 5) = htonl(*(_DWORD *)(v6 + 4));
      *((_DWORD *)v10 + 9) = htonl(*v12);
    }
    *a5 = v10;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180014b74  mov     rax, rsp
0x180014b77  mov     [rax+20h], r9
0x180014b7b  mov     [rax+18h], r8d
0x180014b7f  mov     [rax+10h], rdx
0x180014b83  mov     [rax+8], rcx
0x180014b87  push    rbx
0x180014b88  push    rbp
0x180014b89  push    rsi
0x180014b8a  push    rdi
0x180014b8b  push    r12
0x180014b8d  push    r13
0x180014b8f  push    r14
0x180014b91  push    r15
0x180014b93  sub     rsp, 78h
0x180014b97  mov     esi, [rdx]
0x180014b99  mov     rbp, rcx
0x180014b9c  mov     edi, 134h
0x180014ba1  mov     [rsp+0B8h+var_58], esi
0x180014ba5  mov     ecx, edi
0x180014ba7  mov     r14, r9
0x180014baa  mov     rbx, rdx
0x180014bad  call    cs:__imp_DiscpAllocMemory
0x180014bb3  mov     r13, rax
0x180014bb6  test    rax, rax
0x180014bb9  jz      loc_180014D5F
0x180014bbf  mov     r8d, edi; Size
0x180014bc2  xor     edx, edx; Val
0x180014bc4  mov     rcx, rax; void *
0x180014bc7  call    memset_0
0x180014bcc  lea     rdi, [r13+48h]
0x180014bd0  lea     rcx, [rdi+54h]; pszDest
0x180014bd4  mov     [r14], rcx
0x180014bd7  lea     r14, [rbx+4]
0x180014bdb  mov     [rsp+0B8h+var_50], r14
0x180014be0  test    esi, esi
0x180014be2  jnz     short loc_180014C16
0x180014be4  movzx   edx, byte ptr [rbx+6]
0x180014be8  movzx   r8d, byte ptr [rbx+5]
0x180014bed  movzx   eax, byte ptr [rbx+7]
0x180014bf1  movzx   r9d, byte ptr [r14]
0x180014bf5  mov     [rsp+0B8h+var_88], eax
0x180014bf9  mov     [rsp+0B8h+var_90], edx
0x180014bfd  lea     edx, [rsi+4Ch]; cchDest
0x180014c00  mov     [rsp+0B8h+var_98], r8d
0x180014c05  lea     r8, aIscsiTunnelPol_0; "iSCSI_Tunnel_POLICY_to_%d.%d.%d.%d"
0x180014c0c  call    StringCchPrintfW
0x180014c11  jmp     loc_180014CE2
0x180014c16  movzx   ecx, word ptr [rbx+1Ah]; hostshort
0x180014c1a  call    cs:__imp_htons
0x180014c20  movzx   ecx, word ptr [rbx+18h]; hostshort
0x180014c24  movzx   r12d, ax
0x180014c28  call    cs:__imp_htons
0x180014c2e  movzx   ecx, word ptr [rbx+16h]; hostshort
0x180014c32  movzx   r15d, ax
0x180014c36  call    cs:__imp_htons
0x180014c3c  movzx   ecx, word ptr [rbx+14h]; hostshort
0x180014c40  movzx   r14d, ax
0x180014c44  call    cs:__imp_htons
0x180014c4a  movzx   ecx, word ptr [rbx+12h]; hostshort
0x180014c4e  movzx   ebp, ax
0x180014c51  call    cs:__imp_htons
0x180014c57  movzx   ecx, word ptr [rbx+10h]; hostshort
0x180014c5b  movzx   esi, ax
0x180014c5e  call    cs:__imp_htons
0x180014c64  movzx   ecx, word ptr [rbx+0Eh]; hostshort
0x180014c68  movzx   edi, ax
0x180014c6b  call    cs:__imp_htons
0x180014c71  mov     rcx, [rsp+0B8h+arg_8]
0x180014c79  movzx   ebx, ax
0x180014c7c  movzx   ecx, word ptr [rcx+0Ch]; hostshort
0x180014c80  call    cs:__imp_htons
0x180014c86  mov     rcx, [rsp+0B8h+arg_18]
0x180014c8e  lea     r8, aIscsiTunnelPol; "iSCSI_Tunnel_POLICY_to_%04x:%04x:%04x:%"...
0x180014c95  mov     [rsp+0B8h+var_68], r12d
0x180014c9a  mov     edx, 4Ch ; 'L'; cchDest
0x180014c9f  mov     [rsp+0B8h+var_70], r15d
0x180014ca4  mov     [rsp+0B8h+var_78], r14d
0x180014ca9  mov     rcx, [rcx]; pszDest
0x180014cac  mov     [rsp+0B8h+var_80], ebp
0x180014cb0  mov     [rsp+0B8h+var_88], esi
0x180014cb4  movzx   r9d, ax
0x180014cb8  mov     [rsp+0B8h+var_90], edi
0x180014cbc  mov     [rsp+0B8h+var_98], ebx
0x180014cc0  call    StringCchPrintfW
0x180014cc5  mov     r14, [rsp+0B8h+var_50]
0x180014cca  lea     rdi, [r13+48h]
0x180014cce  mov     rbx, [rsp+0B8h+arg_8]
0x180014cd6  mov     esi, [rsp+0B8h+var_58]
0x180014cda  mov     rbp, [rsp+0B8h+arg_0]
0x180014ce2  mov     r8d, [rsp+0B8h+arg_10]
0x180014cea  mov     rcx, rdi
0x180014ced  call    DiscpFillIpsecProposals
0x180014cf2  test    eax, eax
0x180014cf4  jnz     short loc_180014D64
0x180014cf6  test    esi, esi
0x180014cf8  mov     [r13+0], eax
0x180014cfc  mov     [r13+8], rdi
0x180014d00  setnz   al
0x180014d03  mov     dword ptr [r13+4], 3
0x180014d0b  mov     [r13+10h], eax
0x180014d0f  mov     eax, 168h
0x180014d14  mov     [r13+34h], eax
0x180014d18  mov     [r13+38h], eax
0x180014d1c  test    esi, esi
0x180014d1e  jnz     short loc_180014D3C
0x180014d20  mov     ecx, [rbp+4]; hostlong
0x180014d23  call    cs:__imp_htonl
0x180014d29  mov     [r13+14h], eax
0x180014d2d  mov     ecx, [r14]; hostlong
0x180014d30  call    cs:__imp_htonl
0x180014d36  mov     [r13+24h], eax
0x180014d3a  jmp     short loc_180014D50
0x180014d3c  movups  xmm0, xmmword ptr [rbp+0Ch]
0x180014d40  movdqu  xmmword ptr [r13+14h], xmm0
0x180014d46  movups  xmm1, xmmword ptr [rbx+0Ch]
0x180014d4a  movdqu  xmmword ptr [r13+24h], xmm1
0x180014d50  mov     rax, [rsp+0B8h+arg_20]
0x180014d58  mov     [rax], r13
0x180014d5b  xor     eax, eax
0x180014d5d  jmp     short loc_180014D64
0x180014d5f  mov     eax, 8
0x180014d64  add     rsp, 78h
0x180014d68  pop     r15
0x180014d6a  pop     r14
0x180014d6c  pop     r13
0x180014d6e  pop     r12
0x180014d70  pop     rdi
0x180014d71  pop     rsi
0x180014d72  pop     rbp
0x180014d73  pop     rbx
0x180014d74  retn
```
