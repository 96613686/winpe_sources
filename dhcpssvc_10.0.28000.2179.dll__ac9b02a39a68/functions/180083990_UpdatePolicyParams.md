# UpdatePolicyParams

- ea: `0x180083990`
- end: `0x180083ddf`
- name: `UpdatePolicyParams`
- size: `1103`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180081684`

## callees

- `0x1800250e8`
- `0x1800516fc`
- `0x180058208`
- `0x18007e6b0`
- `0x18007eeb0`
- `0x180082a60`
- `0x180083358`
- `0x1800836c8`
- `0x180083990`
- `0x1800be61c`
- `0x1800cdac0`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800839dd`
- `RPCRT4!RpcImpersonateClient` at `0x1800839dd`
- `RPCRT4!RpcRevertToSelf` at `0x180083d71`
- `RPCRT4!RpcRevertToSelf` at `0x180083d71`
- `WS2_32!__imp_ntohl` at `0x180083a0f`
- `WS2_32!__imp_ntohl` at `0x180083a0f`
- `KERNEL32!HeapFree` at `0x180083d8e`
- `KERNEL32!HeapFree` at `0x180083dab`
- `KERNEL32!HeapFree` at `0x180083d8e`
- `KERNEL32!HeapFree` at `0x180083dab`

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
  unsigned int v15; // edx
  unsigned int v16; // edx
  unsigned int v17; // edx
  unsigned int v18; // edx
  unsigned int v19; // edx
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
  if ( !v15 )
  {
    if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
      goto LABEL_57;
    String = GetString(1148 - (unsigned int)(*(_DWORD *)(a2 + 56) != 0));
    v23 = *(_QWORD *)a2;
    v24 = &UpdateServerPolicyState;
    v25 = String;
    goto LABEL_18;
  }
  v16 = v15 - 1;
  if ( !v16 )
  {
    if ( (Microsoft_Windows_DHCP_ServerEnableBits & 4) == 0 )
      goto LABEL_57;
    LODWORD(v22) = GetString(1148 - (unsigned int)(*(_DWORD *)(a2 + 56) != 0));
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
0x180083990  mov     [rsp-8+arg_0], rbx
0x180083995  push    rbp
0x180083996  push    rsi
0x180083997  push    rdi
0x180083998  push    r12
0x18008399a  push    r13
0x18008399c  push    r14
0x18008399e  push    r15
0x1800839a0  lea     rbp, [rsp-27h]
0x1800839a5  sub     rsp, 0A0h
0x1800839ac  mov     rax, cs:__security_cookie
0x1800839b3  xor     rax, rsp
0x1800839b6  mov     [rbp+57h+var_40], rax
0x1800839ba  xor     r14d, r14d
0x1800839bd  mov     [rbp+57h+var_88], rcx
0x1800839c1  xor     ecx, ecx; BindingHandle
0x1800839c3  mov     [rbp+57h+lpMem], r14
0x1800839c7  mov     edi, r14d
0x1800839ca  mov     [rbp+57h+var_A0], r14
0x1800839ce  mov     esi, r14d
0x1800839d1  mov     r15d, r14d
0x1800839d4  mov     r13, r9
0x1800839d7  mov     r12, r8
0x1800839da  mov     rbx, rdx
0x1800839dd  call    cs:__imp_RpcImpersonateClient
0x1800839e4  nop     dword ptr [rax+rax+00h]
0x1800839e9  xor     r8d, r8d
0x1800839ec  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800839f0  mov     [rbp+57h+var_90], eax
0x1800839f3  cmp     [rbx+8], r8d
0x1800839f7  jnz     short loc_180083A2E
0x1800839f9  test    r13, r13
0x1800839fc  jz      short loc_180083A0C
0x1800839fe  mov     rdi, r14
0x180083a01  inc     rdi
0x180083a04  cmp     [r13+rdi*2+0], r8w
0x180083a0a  jnz     short loc_180083A01
0x180083a0c  mov     ecx, [rbx+0Ch]; netlong
0x180083a0f  call    cs:__imp_ntohl
0x180083a16  nop     dword ptr [rax+rax+00h]
0x180083a1b  mov     r8, rdi
0x180083a1e  mov     rdx, r13
0x180083a21  mov     ecx, eax
0x180083a23  call    FormatIPandName
0x180083a28  mov     rdi, rax
0x180083a2b  xor     r8d, r8d
0x180083a2e  mov     rcx, [rbp+57h+var_88]
0x180083a32  mov     eax, 4F0Ch
0x180083a37  movzx   edx, word ptr [rcx]
0x180083a3a  cmp     edx, eax
0x180083a3c  ja      loc_180083BD7
0x180083a42  jz      loc_180083BB7
0x180083a48  sub     edx, 4EFCh
0x180083a4e  jz      loc_180083B86
0x180083a54  sub     edx, 1
0x180083a57  jz      loc_180083B58
0x180083a5d  sub     edx, 1
0x180083a60  jz      loc_180083B10
0x180083a66  sub     edx, 1
0x180083a69  jz      short loc_180083ABE
0x180083a6b  sub     edx, 0Bh
0x180083a6e  jz      short loc_180083A99
0x180083a70  cmp     edx, 1
0x180083a73  jnz     loc_180083D68
0x180083a79  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x180083a80  jz      loc_180083D68
0x180083a86  mov     r9, [r12]
0x180083a8a  lea     rdx, UpdateScopePolicyName
0x180083a91  mov     r8, [rbx]
0x180083a94  jmp     loc_180083D5E
0x180083a99  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x180083aa0  jz      loc_180083D68
0x180083aa6  mov     r9, [r12]
0x180083aaa  lea     rdx, UpdateServerPolicyName
0x180083ab1  mov     r8, [rbx]
0x180083ab4  call    McTemplateU0zz_EventWriteTransfer
0x180083ab9  jmp     loc_180083D68
0x180083abe  lea     r8, [rbp+57h+var_A0]
0x180083ac2  mov     rcx, rbx
0x180083ac5  lea     rdx, [rbp+57h+lpMem]
0x180083ac9  call    FormatPolicyConditions
0x180083ace  mov     rsi, [rbp+57h+lpMem]
0x180083ad2  xor     r14d, r14d
0x180083ad5  test    rsi, rsi
0x180083ad8  jz      loc_180083D6B
0x180083ade  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x180083ae5  jz      loc_180083D6B
0x180083aeb  mov     rax, [rbx]
0x180083aee  lea     rdx, UpdateScopePolicyExpr
0x180083af5  mov     r9, [rbp+57h+var_A0]
0x180083af9  mov     r8, rsi
0x180083afc  mov     [rsp+0D0h+var_A8], rdi
0x180083b01  mov     [rsp+0D0h+var_B0], rax
0x180083b06  call    McTemplateU0zzzz_EventWriteTransfer
0x180083b0b  jmp     loc_180083D6B
0x180083b10  lea     r8, [rbp+57h+var_A0]
0x180083b14  mov     rcx, rbx
0x180083b17  lea     rdx, [rbp+57h+lpMem]
0x180083b1b  call    FormatPolicyConditions
0x180083b20  mov     rsi, [rbp+57h+lpMem]
0x180083b24  xor     r14d, r14d
0x180083b27  test    rsi, rsi
0x180083b2a  jz      loc_180083D6B
0x180083b30  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x180083b37  jz      loc_180083D6B
0x180083b3d  mov     rax, [rbx]
0x180083b40  lea     rdx, UpdateServerPolicyExpr
0x180083b47  mov     r9, [rbp+57h+var_A0]
0x180083b4b  mov     r8, rsi
0x180083b4e  mov     [rsp+0D0h+var_B0], rax
0x180083b53  jmp     loc_180083C7C
0x180083b58  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x180083b5f  jz      loc_180083D68
0x180083b65  mov     eax, [rbx+38h]
0x180083b68  neg     eax
0x180083b6a  sbb     ecx, ecx
0x180083b6c  add     ecx, 47Ch
0x180083b72  call    GetString
0x180083b77  mov     r8, rax
0x180083b7a  lea     rdx, UpdateScopePolicyState
0x180083b81  jmp     loc_180083D5B
0x180083b86  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x180083b8d  jz      loc_180083D68
0x180083b93  mov     eax, [rbx+38h]
0x180083b96  neg     eax
0x180083b98  sbb     ecx, ecx
0x180083b9a  add     ecx, 47Ch
0x180083ba0  call    GetString
0x180083ba5  mov     r9, [rbx]
0x180083ba8  lea     rdx, UpdateServerPolicyState
0x180083baf  mov     r8, rax
0x180083bb2  jmp     loc_180083AB4
0x180083bb7  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x180083bbe  jz      loc_180083D68
0x180083bc4  mov     r9, [rbx]
0x180083bc7  lea     rdx, UpdateServerPolicyDescription
0x180083bce  mov     r8, [rbx+30h]
0x180083bd2  jmp     loc_180083AB4
0x180083bd7  sub     edx, 4F0Dh
0x180083bdd  jz      loc_180083D47
0x180083be3  sub     edx, 1
0x180083be6  jz      loc_180083CBA
0x180083bec  sub     edx, 1
0x180083bef  jz      loc_180083C86
0x180083bf5  sub     edx, 4Ch ; 'L'
0x180083bf8  jz      short loc_180083C42
0x180083bfa  cmp     edx, 1
0x180083bfd  jnz     loc_180083D68
0x180083c03  mov     rcx, [rbx+40h]
0x180083c07  xor     edx, edx
0x180083c09  lea     r8d, [rdx+3]
0x180083c0d  call    DhcpHlprFindV4DhcpPropertyInternal
0x180083c12  xor     r14d, r14d
0x180083c15  test    rax, rax
0x180083c18  jz      short loc_180083C1E
0x180083c1a  mov     r15, [rax+8]
0x180083c1e  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x180083c25  jz      loc_180083D6B
0x180083c2b  mov     r9, [rbx]
0x180083c2e  lea     rdx, UpdateServerPolicyDNSSuffix
0x180083c35  mov     r8, r15
0x180083c38  call    McTemplateU0zz_EventWriteTransfer
0x180083c3d  jmp     loc_180083D6B
0x180083c42  mov     rcx, [rbx+40h]
0x180083c46  xor     edx, edx
0x180083c48  lea     r8d, [rdx+3]
0x180083c4c  call    DhcpHlprFindV4DhcpPropertyInternal
0x180083c51  xor     r14d, r14d
0x180083c54  test    rax, rax
0x180083c57  jz      short loc_180083C5D
0x180083c59  mov     r15, [rax+8]
0x180083c5d  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x180083c64  jz      loc_180083D6B
0x180083c6a  mov     r9, [rbx]
0x180083c6d  lea     rdx, UpdateScopePolicyDNSSuffix
0x180083c74  mov     [rsp+0D0h+var_B0], rdi
0x180083c79  mov     r8, r15
0x180083c7c  call    McTemplateU0zzz_EventWriteTransfer
0x180083c81  jmp     loc_180083D6B
0x180083c86  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x180083c8d  jz      loc_180083D68
0x180083c93  mov     rax, [rbx]
0x180083c96  lea     rdx, UpdateScopePolicyProcOrder
0x180083c9d  mov     r9d, [r12+10h]
0x180083ca2  mov     r8d, [rbx+10h]
0x180083ca6  mov     [rsp+0D0h+var_A8], rdi
0x180083cab  mov     [rsp+0D0h+var_B0], rax
0x180083cb0  call    McTemplateU0qqzz_EventWriteTransfer
0x180083cb5  jmp     loc_180083D68
0x180083cba  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x180083cc1  jz      loc_180083D68
0x180083cc7  mov     eax, [r12+10h]
0x180083ccc  mov     rcx, [rbx]
0x180083ccf  mov     dword ptr [rbp+57h+lpMem], eax
0x180083cd2  mov     eax, [rbx+10h]
0x180083cd5  mov     dword ptr [rbp+57h+var_A0], eax
0x180083cd8  lea     rax, [rbp+57h+var_A0]
0x180083cdc  mov     [rbp+57h+var_70], rax
0x180083ce0  lea     rax, [rbp+57h+lpMem]
0x180083ce4  mov     [rbp+57h+var_60], rax
0x180083ce8  mov     [rbp+57h+var_68], 4
0x180083cf0  mov     [rbp+57h+var_58], 4
0x180083cf8  test    rcx, rcx
0x180083cfb  jz      short loc_180083D11
0x180083cfd  inc     r14
0x180083d00  cmp     [rcx+r14*2], r8w
0x180083d05  jnz     short loc_180083CFD
0x180083d07  lea     r14d, ds:2[r14*2]
0x180083d0f  jmp     short loc_180083D1E
0x180083d11  mov     r14d, 0Ah
0x180083d17  lea     rcx, aNull_0; "NULL"
0x180083d1e  lea     rax, [rbp+57h+var_80]
0x180083d22  mov     [rbp+57h+var_50], rcx
0x180083d26  mov     r9d, 4
0x180083d2c  mov     [rsp+0D0h+var_B0], rax
0x180083d31  lea     rdx, UpdateServerPolicyProcOrder
0x180083d38  mov     [rbp+57h+var_48], r14d
0x180083d3c  mov     [rbp+57h+var_44], r8d
0x180083d40  call    McGenEventWrite_EventWriteTransfer
0x180083d45  jmp     short loc_180083D68
0x180083d47  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, 4
0x180083d4e  jz      short loc_180083D68
0x180083d50  mov     r8, [rbx+30h]
0x180083d54  lea     rdx, UpdateScopePolicyDescription
0x180083d5b  mov     r9, [rbx]
0x180083d5e  mov     [rsp+0D0h+var_B0], rdi
0x180083d63  call    McTemplateU0zzz_EventWriteTransfer
0x180083d68  xor     r14d, r14d
0x180083d6b  cmp     [rbp+57h+var_90], r14d
0x180083d6f  jnz     short loc_180083D7D
0x180083d71  call    cs:__imp_RpcRevertToSelf
0x180083d78  nop     dword ptr [rax+rax+00h]
0x180083d7d  test    rsi, rsi
0x180083d80  jz      short loc_180083D9A
0x180083d82  mov     rcx, cs:gDhcpHeap; hHeap
0x180083d89  mov     r8, rsi; lpMem
0x180083d8c  xor     edx, edx; dwFlags
0x180083d8e  call    cs:__imp_HeapFree
0x180083d95  nop     dword ptr [rax+rax+00h]
0x180083d9a  test    rdi, rdi
0x180083d9d  jz      short loc_180083DB7
0x180083d9f  mov     rcx, cs:gDhcpHeap; hHeap
0x180083da6  mov     r8, rdi; lpMem
0x180083da9  xor     edx, edx; dwFlags
0x180083dab  call    cs:__imp_HeapFree
0x180083db2  nop     dword ptr [rax+rax+00h]
0x180083db7  mov     rcx, [rbp+57h+var_40]
0x180083dbb  xor     rcx, rsp; StackCookie
0x180083dbe  call    __security_check_cookie
0x180083dc3  mov     rbx, [rsp+0D0h+arg_0]
0x180083dcb  add     rsp, 0A0h
0x180083dd2  pop     r15
0x180083dd4  pop     r14
0x180083dd6  pop     r13
0x180083dd8  pop     r12
0x180083dda  pop     rdi
0x180083ddb  pop     rsi
0x180083ddc  pop     rbp
0x180083ddd  retn
```
