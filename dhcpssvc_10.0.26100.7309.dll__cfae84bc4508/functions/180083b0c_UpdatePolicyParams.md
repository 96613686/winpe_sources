# UpdatePolicyParams

- ea: `0x180083b0c`
- end: `0x180083f5b`
- name: `UpdatePolicyParams`
- size: `1103`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800817bc`

## callees

- `0x180025b98`
- `0x1800519fc`
- `0x180058530`
- `0x18007e7c8`
- `0x18007efb4`
- `0x180082b88`
- `0x1800834a4`
- `0x180083838`
- `0x180083b0c`
- `0x1800bd748`
- `0x1800cc9e0`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180083b59`
- `RPCRT4!RpcImpersonateClient` at `0x180083b59`
- `RPCRT4!RpcRevertToSelf` at `0x180083eed`
- `RPCRT4!RpcRevertToSelf` at `0x180083eed`
- `WS2_32!__imp_ntohl` at `0x180083b8b`
- `WS2_32!__imp_ntohl` at `0x180083b8b`
- `KERNEL32!HeapFree` at `0x180083f0a`
- `KERNEL32!HeapFree` at `0x180083f27`
- `KERNEL32!HeapFree` at `0x180083f0a`
- `KERNEL32!HeapFree` at `0x180083f27`

## pseudocode

```c
int __fastcall UpdatePolicyParams(unsigned __int16 *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rdi
  void *v5; // rsi
  __int64 v6; // r15
  __int64 v10; // r14
  u_long v11; // eax
  unsigned __int16 *v12; // rcx
  __int64 V4DhcpPropertyInternal; // rax
  unsigned int v14; // edx
  __int64 v15; // rdx
  __int64 v16; // rdx
  int v17; // edx
  int v18; // edx
  int v19; // edx
  __int64 v20; // r9
  __int128 *v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int128 *v24; // rdx
  __int64 v25; // r8
  int v26; // ecx
  int v27; // ecx
  __int64 String; // rax
  unsigned int v29; // edx
  unsigned int v30; // edx
  unsigned int v31; // edx
  unsigned int v32; // edx
  __int64 v33; // rcx
  int v34; // ecx
  const wchar_t *v35; // rcx
  int v36; // r14d
  __int64 v38; // [rsp+30h] [rbp-49h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-41h] BYREF
  RPC_STATUS v40; // [rsp+40h] [rbp-39h]
  unsigned __int16 *v41; // [rsp+48h] [rbp-31h]
  struct _EVENT_DATA_DESCRIPTOR v42; // [rsp+50h] [rbp-29h] BYREF
  __int64 *v43; // [rsp+60h] [rbp-19h]
  __int64 v44; // [rsp+68h] [rbp-11h]
  LPVOID *p_lpMem; // [rsp+70h] [rbp-9h]
  __int64 v46; // [rsp+78h] [rbp-1h]
  const wchar_t *v47; // [rsp+80h] [rbp+7h]
  int v48; // [rsp+88h] [rbp+Fh]
  int v49; // [rsp+8Ch] [rbp+13h]

  v41 = a1;
  lpMem = 0;
  v4 = 0;
  v38 = 0;
  v5 = 0;
  v6 = 0;
  v10 = -1;
  v40 = RpcImpersonateClient(0);
  if ( !*(_DWORD *)(a2 + 8) )
  {
    if ( a4 )
    {
      v4 = -1;
      do
        ++v4;
      while ( *(_WORD *)(a4 + 2 * v4) );
    }
    v11 = ntohl(*(_DWORD *)(a2 + 12));
    v4 = FormatIPandName(v11, a4, v4);
  }
  v12 = v41;
  LODWORD(V4DhcpPropertyInternal) = 20236;
  v14 = *v41;
  if ( v14 > 0x4F0C )
  {
    v29 = v14 - 20237;
    if ( v29 )
    {
      v30 = v29 - 1;
      if ( v30 )
      {
        v31 = v30 - 1;
        if ( v31 )
        {
          v32 = v31 - 76;
          if ( v32 )
          {
            if ( v32 == 1 )
            {
              V4DhcpPropertyInternal = DhcpHlprFindV4DhcpPropertyInternal(*(_QWORD *)(a2 + 64), 0, 3);
              if ( V4DhcpPropertyInternal )
                v6 = *(_QWORD *)(V4DhcpPropertyInternal + 8);
              if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) != 0 )
                LODWORD(V4DhcpPropertyInternal) = McTemplateU0zz_EventWriteTransfer(
                                                    v33,
                                                    &UpdateServerPolicyDNSSuffix,
                                                    v6,
                                                    *(_QWORD *)a2);
            }
          }
          else
          {
            V4DhcpPropertyInternal = DhcpHlprFindV4DhcpPropertyInternal(*(_QWORD *)(a2 + 64), 0, 3);
            if ( V4DhcpPropertyInternal )
              v6 = *(_QWORD *)(V4DhcpPropertyInternal + 8);
            if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) != 0 )
              LODWORD(V4DhcpPropertyInternal) = McTemplateU0zzz_EventWriteTransfer(
                                                  v34,
                                                  (unsigned int)&UpdateScopePolicyDNSSuffix,
                                                  v6,
                                                  *(_QWORD *)a2,
                                                  v4);
          }
        }
        else if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) != 0 )
        {
          LODWORD(V4DhcpPropertyInternal) = McTemplateU0qqzz_EventWriteTransfer(
                                              (_DWORD)v41,
                                              (unsigned int)&UpdateScopePolicyProcOrder,
                                              *(_DWORD *)(a2 + 16),
                                              *(_DWORD *)(a3 + 16),
                                              *(_QWORD *)a2,
                                              v4);
        }
      }
      else if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) != 0 )
      {
        v35 = *(const wchar_t **)a2;
        LODWORD(lpMem) = *(_DWORD *)(a3 + 16);
        LODWORD(v38) = *(_DWORD *)(a2 + 16);
        v43 = &v38;
        p_lpMem = &lpMem;
        v44 = 4;
        v46 = 4;
        if ( v35 )
        {
          do
            ++v10;
          while ( v35[v10] );
          v36 = 2 * v10 + 2;
        }
        else
        {
          v36 = 10;
          v35 = L"NULL";
        }
        v47 = v35;
        v48 = v36;
        v49 = 0;
        LODWORD(V4DhcpPropertyInternal) = McGenEventWrite_EventWriteTransfer(
                                            (__int64)v35,
                                            (const EVENT_DESCRIPTOR *)&UpdateServerPolicyProcOrder,
                                            0,
                                            4u,
                                            &v42);
      }
      goto LABEL_57;
    }
    if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
      goto LABEL_57;
    v22 = *(_QWORD *)(a2 + 48);
    v21 = &UpdateScopePolicyDescription;
LABEL_55:
    v20 = *(_QWORD *)a2;
    goto LABEL_56;
  }
  if ( v14 == 20236 )
  {
    if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
      goto LABEL_57;
    v23 = *(_QWORD *)a2;
    v24 = &UpdateServerPolicyDescription;
    v25 = *(_QWORD *)(a2 + 48);
LABEL_18:
    LODWORD(V4DhcpPropertyInternal) = McTemplateU0zz_EventWriteTransfer(v12, v24, v25, v23);
    goto LABEL_57;
  }
  v15 = v14 - 20220;
  if ( !(_DWORD)v15 )
  {
    if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
      goto LABEL_57;
    String = GetString(1148 - (unsigned int)(*(_DWORD *)(a2 + 56) != 0), v15, 0);
    v23 = *(_QWORD *)a2;
    v24 = &UpdateServerPolicyState;
    v25 = String;
    goto LABEL_18;
  }
  v16 = (unsigned int)(v15 - 1);
  if ( !(_DWORD)v16 )
  {
    if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
      goto LABEL_57;
    LODWORD(v22) = GetString(1148 - (unsigned int)(*(_DWORD *)(a2 + 56) != 0), v16, 0);
    v21 = &UpdateScopePolicyState;
    goto LABEL_55;
  }
  v17 = v16 - 1;
  if ( !v17 )
  {
    LODWORD(V4DhcpPropertyInternal) = FormatPolicyConditions(a2, &lpMem, &v38);
    v5 = lpMem;
    if ( lpMem && (Microsoft_Windows_DHCP_ServerEnableBits & 4) != 0 )
      LODWORD(V4DhcpPropertyInternal) = McTemplateU0zzz_EventWriteTransfer(
                                          v27,
                                          (unsigned int)&UpdateServerPolicyExpr,
                                          (_DWORD)lpMem,
                                          v38,
                                          *(_QWORD *)a2);
    goto LABEL_57;
  }
  v18 = v17 - 1;
  if ( !v18 )
  {
    LODWORD(V4DhcpPropertyInternal) = FormatPolicyConditions(a2, &lpMem, &v38);
    v5 = lpMem;
    if ( lpMem && (Microsoft_Windows_DHCP_ServerEnableBits & 4) != 0 )
      LODWORD(V4DhcpPropertyInternal) = McTemplateU0zzzz_EventWriteTransfer(
                                          v26,
                                          (unsigned int)&UpdateScopePolicyExpr,
                                          (_DWORD)lpMem,
                                          v38,
                                          *(_QWORD *)a2,
                                          v4);
    goto LABEL_57;
  }
  v19 = v18 - 11;
  if ( !v19 )
  {
    if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
      goto LABEL_57;
    v23 = *(_QWORD *)a3;
    v24 = &UpdateServerPolicyName;
    v25 = *(_QWORD *)a2;
    goto LABEL_18;
  }
  if ( v19 == 1 && (Microsoft_Windows_DHCP_ServerEnableBits & 4) != 0 )
  {
    v20 = *(_QWORD *)a3;
    v21 = &UpdateScopePolicyName;
    v22 = *(_QWORD *)a2;
LABEL_56:
    LODWORD(V4DhcpPropertyInternal) = McTemplateU0zzz_EventWriteTransfer((_DWORD)v12, (_DWORD)v21, v22, v20, v4);
  }
LABEL_57:
  if ( !v40 )
    LODWORD(V4DhcpPropertyInternal) = RpcRevertToSelf();
  if ( v5 )
    LODWORD(V4DhcpPropertyInternal) = HeapFree(gDhcpHeap, 0, v5);
  if ( v4 )
    LODWORD(V4DhcpPropertyInternal) = HeapFree(gDhcpHeap, 0, (LPVOID)v4);
  return V4DhcpPropertyInternal;
}

```

## disassembly

```asm
0x180083b0c  mov     [rsp-8+arg_0], rbx
0x180083b11  push    rbp
0x180083b12  push    rsi
0x180083b13  push    rdi
0x180083b14  push    r12
0x180083b16  push    r13
0x180083b18  push    r14
0x180083b1a  push    r15
0x180083b1c  lea     rbp, [rsp-27h]
0x180083b21  sub     rsp, 0A0h
0x180083b28  mov     rax, cs:__security_cookie
0x180083b2f  xor     rax, rsp
0x180083b32  mov     [rbp+57h+var_40], rax
0x180083b36  xor     r14d, r14d
0x180083b39  mov     [rbp+57h+var_88], rcx
0x180083b3d  xor     ecx, ecx; BindingHandle
0x180083b3f  mov     [rbp+57h+lpMem], r14
0x180083b43  mov     edi, r14d
0x180083b46  mov     [rbp+57h+var_A0], r14
0x180083b4a  mov     esi, r14d
0x180083b4d  mov     r15d, r14d
0x180083b50  mov     r13, r9
0x180083b53  mov     r12, r8
0x180083b56  mov     rbx, rdx
0x180083b59  call    cs:__imp_RpcImpersonateClient
0x180083b60  nop     dword ptr [rax+rax+00h]
0x180083b65  xor     r8d, r8d
0x180083b68  or      r14, 0FFFFFFFFFFFFFFFFh
0x180083b6c  mov     [rbp+57h+var_90], eax
0x180083b6f  cmp     [rbx+8], r8d
0x180083b73  jnz     short loc_180083BAA
0x180083b75  test    r13, r13
0x180083b78  jz      short loc_180083B88
0x180083b7a  mov     rdi, r14
0x180083b7d  inc     rdi
0x180083b80  cmp     [r13+rdi*2+0], r8w
0x180083b86  jnz     short loc_180083B7D
0x180083b88  mov     ecx, [rbx+0Ch]; netlong
0x180083b8b  call    cs:__imp_ntohl
0x180083b92  nop     dword ptr [rax+rax+00h]
0x180083b97  mov     r8, rdi
0x180083b9a  mov     rdx, r13
0x180083b9d  mov     ecx, eax
0x180083b9f  call    FormatIPandName
0x180083ba4  mov     rdi, rax
0x180083ba7  xor     r8d, r8d
0x180083baa  mov     rcx, [rbp+57h+var_88]
0x180083bae  mov     eax, 4F0Ch
0x180083bb3  movzx   edx, word ptr [rcx]
0x180083bb6  cmp     edx, eax
0x180083bb8  ja      loc_180083D53
0x180083bbe  jz      loc_180083D33
0x180083bc4  sub     edx, 4EFCh
0x180083bca  jz      loc_180083D02
0x180083bd0  sub     edx, 1
0x180083bd3  jz      loc_180083CD4
0x180083bd9  sub     edx, 1
0x180083bdc  jz      loc_180083C8C
0x180083be2  sub     edx, 1
0x180083be5  jz      short loc_180083C3A
0x180083be7  sub     edx, 0Bh
0x180083bea  jz      short loc_180083C15
0x180083bec  cmp     edx, 1
0x180083bef  jnz     loc_180083EE4
0x180083bf5  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x180083bfc  jz      loc_180083EE4
0x180083c02  mov     r9, [r12]
0x180083c06  lea     rdx, UpdateScopePolicyName
0x180083c0d  mov     r8, [rbx]
0x180083c10  jmp     loc_180083EDA
0x180083c15  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x180083c1c  jz      loc_180083EE4
0x180083c22  mov     r9, [r12]
0x180083c26  lea     rdx, UpdateServerPolicyName
0x180083c2d  mov     r8, [rbx]
0x180083c30  call    McTemplateU0zz_EventWriteTransfer
0x180083c35  jmp     loc_180083EE4
0x180083c3a  lea     r8, [rbp+57h+var_A0]
0x180083c3e  mov     rcx, rbx
0x180083c41  lea     rdx, [rbp+57h+lpMem]
0x180083c45  call    FormatPolicyConditions
0x180083c4a  mov     rsi, [rbp+57h+lpMem]
0x180083c4e  xor     r14d, r14d
0x180083c51  test    rsi, rsi
0x180083c54  jz      loc_180083EE7
0x180083c5a  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x180083c61  jz      loc_180083EE7
0x180083c67  mov     rax, [rbx]
0x180083c6a  lea     rdx, UpdateScopePolicyExpr
0x180083c71  mov     r9, [rbp+57h+var_A0]
0x180083c75  mov     r8, rsi
0x180083c78  mov     [rsp+0D0h+var_A8], rdi
0x180083c7d  mov     [rsp+0D0h+var_B0], rax
0x180083c82  call    McTemplateU0zzzz_EventWriteTransfer
0x180083c87  jmp     loc_180083EE7
0x180083c8c  lea     r8, [rbp+57h+var_A0]
0x180083c90  mov     rcx, rbx
0x180083c93  lea     rdx, [rbp+57h+lpMem]
0x180083c97  call    FormatPolicyConditions
0x180083c9c  mov     rsi, [rbp+57h+lpMem]
0x180083ca0  xor     r14d, r14d
0x180083ca3  test    rsi, rsi
0x180083ca6  jz      loc_180083EE7
0x180083cac  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x180083cb3  jz      loc_180083EE7
0x180083cb9  mov     rax, [rbx]
0x180083cbc  lea     rdx, UpdateServerPolicyExpr
0x180083cc3  mov     r9, [rbp+57h+var_A0]
0x180083cc7  mov     r8, rsi
0x180083cca  mov     [rsp+0D0h+var_B0], rax
0x180083ccf  jmp     loc_180083DF8
0x180083cd4  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x180083cdb  jz      loc_180083EE4
0x180083ce1  mov     eax, [rbx+38h]
0x180083ce4  neg     eax
0x180083ce6  sbb     ecx, ecx
0x180083ce8  add     ecx, 47Ch
0x180083cee  call    GetString
0x180083cf3  mov     r8, rax
0x180083cf6  lea     rdx, UpdateScopePolicyState
0x180083cfd  jmp     loc_180083ED7
0x180083d02  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x180083d09  jz      loc_180083EE4
0x180083d0f  mov     eax, [rbx+38h]
0x180083d12  neg     eax
0x180083d14  sbb     ecx, ecx
0x180083d16  add     ecx, 47Ch
0x180083d1c  call    GetString
0x180083d21  mov     r9, [rbx]
0x180083d24  lea     rdx, UpdateServerPolicyState
0x180083d2b  mov     r8, rax
0x180083d2e  jmp     loc_180083C30
0x180083d33  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x180083d3a  jz      loc_180083EE4
0x180083d40  mov     r9, [rbx]
0x180083d43  lea     rdx, UpdateServerPolicyDescription
0x180083d4a  mov     r8, [rbx+30h]
0x180083d4e  jmp     loc_180083C30
0x180083d53  sub     edx, 4F0Dh
0x180083d59  jz      loc_180083EC3
0x180083d5f  sub     edx, 1
0x180083d62  jz      loc_180083E36
0x180083d68  sub     edx, 1
0x180083d6b  jz      loc_180083E02
0x180083d71  sub     edx, 4Ch ; 'L'
0x180083d74  jz      short loc_180083DBE
0x180083d76  cmp     edx, 1
0x180083d79  jnz     loc_180083EE4
0x180083d7f  mov     rcx, [rbx+40h]
0x180083d83  xor     edx, edx
0x180083d85  lea     r8d, [rdx+3]
0x180083d89  call    DhcpHlprFindV4DhcpPropertyInternal
0x180083d8e  xor     r14d, r14d
0x180083d91  test    rax, rax
0x180083d94  jz      short loc_180083D9A
0x180083d96  mov     r15, [rax+8]
0x180083d9a  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x180083da1  jz      loc_180083EE7
0x180083da7  mov     r9, [rbx]
0x180083daa  lea     rdx, UpdateServerPolicyDNSSuffix
0x180083db1  mov     r8, r15
0x180083db4  call    McTemplateU0zz_EventWriteTransfer
0x180083db9  jmp     loc_180083EE7
0x180083dbe  mov     rcx, [rbx+40h]
0x180083dc2  xor     edx, edx
0x180083dc4  lea     r8d, [rdx+3]
0x180083dc8  call    DhcpHlprFindV4DhcpPropertyInternal
0x180083dcd  xor     r14d, r14d
0x180083dd0  test    rax, rax
0x180083dd3  jz      short loc_180083DD9
0x180083dd5  mov     r15, [rax+8]
0x180083dd9  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x180083de0  jz      loc_180083EE7
0x180083de6  mov     r9, [rbx]
0x180083de9  lea     rdx, UpdateScopePolicyDNSSuffix
0x180083df0  mov     [rsp+0D0h+var_B0], rdi
0x180083df5  mov     r8, r15
0x180083df8  call    McTemplateU0zzz_EventWriteTransfer
0x180083dfd  jmp     loc_180083EE7
0x180083e02  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x180083e09  jz      loc_180083EE4
0x180083e0f  mov     rax, [rbx]
0x180083e12  lea     rdx, UpdateScopePolicyProcOrder
0x180083e19  mov     r9d, [r12+10h]
0x180083e1e  mov     r8d, [rbx+10h]
0x180083e22  mov     [rsp+0D0h+var_A8], rdi
0x180083e27  mov     [rsp+0D0h+var_B0], rax
0x180083e2c  call    McTemplateU0qqzz_EventWriteTransfer
0x180083e31  jmp     loc_180083EE4
0x180083e36  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x180083e3d  jz      loc_180083EE4
0x180083e43  mov     eax, [r12+10h]
0x180083e48  mov     rcx, [rbx]
0x180083e4b  mov     dword ptr [rbp+57h+lpMem], eax
0x180083e4e  mov     eax, [rbx+10h]
0x180083e51  mov     dword ptr [rbp+57h+var_A0], eax
0x180083e54  lea     rax, [rbp+57h+var_A0]
0x180083e58  mov     [rbp+57h+var_70], rax
0x180083e5c  lea     rax, [rbp+57h+lpMem]
0x180083e60  mov     [rbp+57h+var_60], rax
0x180083e64  mov     [rbp+57h+var_68], 4
0x180083e6c  mov     [rbp+57h+var_58], 4
0x180083e74  test    rcx, rcx
0x180083e77  jz      short loc_180083E8D
0x180083e79  inc     r14
0x180083e7c  cmp     [rcx+r14*2], r8w
0x180083e81  jnz     short loc_180083E79
0x180083e83  lea     r14d, ds:2[r14*2]
0x180083e8b  jmp     short loc_180083E9A
0x180083e8d  mov     r14d, 0Ah
0x180083e93  lea     rcx, aNull_0; "NULL"
0x180083e9a  lea     rax, [rbp+57h+var_80]
0x180083e9e  mov     [rbp+57h+var_50], rcx
0x180083ea2  mov     r9d, 4
0x180083ea8  mov     [rsp+0D0h+var_B0], rax
0x180083ead  lea     rdx, UpdateServerPolicyProcOrder
0x180083eb4  mov     [rbp+57h+var_48], r14d
0x180083eb8  mov     [rbp+57h+var_44], r8d
0x180083ebc  call    McGenEventWrite_EventWriteTransfer
0x180083ec1  jmp     short loc_180083EE4
0x180083ec3  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x180083eca  jz      short loc_180083EE4
0x180083ecc  mov     r8, [rbx+30h]
0x180083ed0  lea     rdx, UpdateScopePolicyDescription
0x180083ed7  mov     r9, [rbx]
0x180083eda  mov     [rsp+0D0h+var_B0], rdi
0x180083edf  call    McTemplateU0zzz_EventWriteTransfer
0x180083ee4  xor     r14d, r14d
0x180083ee7  cmp     [rbp+57h+var_90], r14d
0x180083eeb  jnz     short loc_180083EF9
0x180083eed  call    cs:__imp_RpcRevertToSelf
0x180083ef4  nop     dword ptr [rax+rax+00h]
0x180083ef9  test    rsi, rsi
0x180083efc  jz      short loc_180083F16
0x180083efe  mov     rcx, cs:gDhcpHeap; hHeap
0x180083f05  mov     r8, rsi; lpMem
0x180083f08  xor     edx, edx; dwFlags
0x180083f0a  call    cs:__imp_HeapFree
0x180083f11  nop     dword ptr [rax+rax+00h]
0x180083f16  test    rdi, rdi
0x180083f19  jz      short loc_180083F33
0x180083f1b  mov     rcx, cs:gDhcpHeap; hHeap
0x180083f22  mov     r8, rdi; lpMem
0x180083f25  xor     edx, edx; dwFlags
0x180083f27  call    cs:__imp_HeapFree
0x180083f2e  nop     dword ptr [rax+rax+00h]
0x180083f33  mov     rcx, [rbp+57h+var_40]
0x180083f37  xor     rcx, rsp; StackCookie
0x180083f3a  call    __security_check_cookie
0x180083f3f  mov     rbx, [rsp+0D0h+arg_0]
0x180083f47  add     rsp, 0A0h
0x180083f4e  pop     r15
0x180083f50  pop     r14
0x180083f52  pop     r13
0x180083f54  pop     r12
0x180083f56  pop     rdi
0x180083f57  pop     rsi
0x180083f58  pop     rbp
0x180083f59  retn
```
