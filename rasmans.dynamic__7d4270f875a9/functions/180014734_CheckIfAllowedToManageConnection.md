# CheckIfAllowedToManageConnection

- ea: `0x180014734`
- end: `0x1800148bf`
- name: `CheckIfAllowedToManageConnection`
- size: `395`
- prototype: `__int64 __fastcall(PSID pSid2)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019f40`
- `0x180021ae0`
- `0x180021e2c`
- `0x180032a30`

## callees

- `0x180005bcc`
- `0x18000c37c`
- `0x180014734`
- `0x180040580`
- `0x1800425a4`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800147ec`
- `RPCRT4!RpcImpersonateClient` at `0x1800147ec`
- `RPCRT4!RpcRevertToSelf` at `0x18001485f`
- `RPCRT4!RpcRevertToSelf` at `0x18001485f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001481b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001481b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014873`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014873`

## pseudocode

```c
__int64 __fastcall CheckIfAllowedToManageConnection(PSID pSid2, int a2, int a3)
{
  unsigned int v6; // ebx
  __int64 v7; // r9
  struct _LIST_ENTRY *v8; // rcx
  int UserSidFromToken; // eax
  PSID v10; // rdi
  PSID pSid1; // [rsp+78h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 174, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
  }
  pSid1 = 0;
  v6 = 1;
  if ( (unsigned int)FRasmanAccessCheck(a3 != 0 ? 31 : 15) )
    goto LABEL_22;
  if ( !a2 )
  {
    if ( RpcImpersonateClient(0) )
    {
      v6 = 0;
    }
    else
    {
      UserSidFromToken = GetUserSidFromToken(0, &pSid1);
      v10 = pSid1;
      if ( UserSidFromToken )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 176, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
        }
        v6 = 0;
      }
      else
      {
        v6 = EqualSid(pSid1, pSid2);
      }
      RpcRevertToSelf();
      if ( v10 )
        LocalFree(v10);
    }
    goto LABEL_22;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return v6;
  if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 175, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
LABEL_22:
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v8[1].Blink) & 0x2000) != 0
    && BYTE1(v8[1].Blink) >= 6u )
  {
    LOBYTE(v7) = v6;
    WPP_SF_c(v8[1].Flink, 177, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v7);
  }
  return v6;
}

```

## disassembly

```asm
0x180014734  push    rbx
0x180014736  push    rbp
0x180014737  push    rsi
0x180014738  push    rdi
0x180014739  push    r14
0x18001473b  push    r15
0x18001473d  sub     rsp, 28h
0x180014741  mov     edi, r8d
0x180014744  mov     esi, edx
0x180014746  mov     rbp, rcx
0x180014749  mov     rcx, cs:WPP_GLOBAL_Control
0x180014750  lea     r15, WPP_GLOBAL_Control
0x180014757  mov     r14d, 2000h
0x18001475d  cmp     rcx, r15
0x180014760  jz      short loc_180014783
0x180014762  test    [rcx+1Ch], r14d
0x180014766  jz      short loc_180014783
0x180014768  cmp     byte ptr [rcx+19h], 6
0x18001476c  jb      short loc_180014783
0x18001476e  mov     rcx, [rcx+10h]
0x180014772  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180014779  mov     edx, 0AEh
0x18001477e  call    WPP_SF_
0x180014783  neg     edi
0x180014785  mov     [rsp+58h+pSid1], 0
0x18001478e  mov     ebx, 1
0x180014793  sbb     ecx, ecx
0x180014795  and     ecx, 10h
0x180014798  add     ecx, 0Fh
0x18001479b  call    FRasmanAccessCheck
0x1800147a0  test    eax, eax
0x1800147a2  jnz     loc_18001487F
0x1800147a8  test    esi, esi
0x1800147aa  jz      short loc_1800147EA
0x1800147ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800147b3  cmp     rcx, r15
0x1800147b6  jz      loc_1800148AF
0x1800147bc  test    [rcx+1Ch], r14d
0x1800147c0  jz      loc_180014886
0x1800147c6  cmp     byte ptr [rcx+19h], 4
0x1800147ca  jb      loc_180014886
0x1800147d0  mov     rcx, [rcx+10h]
0x1800147d4  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x1800147db  mov     edx, 0AFh
0x1800147e0  call    WPP_SF_
0x1800147e5  jmp     loc_18001487F
0x1800147ea  xor     ecx, ecx; BindingHandle
0x1800147ec  call    cs:__imp_RpcImpersonateClient
0x1800147f3  nop     dword ptr [rax+rax+00h]
0x1800147f8  test    eax, eax
0x1800147fa  jz      short loc_180014800
0x1800147fc  xor     ebx, ebx
0x1800147fe  jmp     short loc_18001487F
0x180014800  lea     rdx, [rsp+58h+pSid1]
0x180014805  xor     ecx, ecx
0x180014807  call    GetUserSidFromToken
0x18001480c  mov     rdi, [rsp+58h+pSid1]
0x180014811  test    eax, eax
0x180014813  jnz     short loc_180014830
0x180014815  mov     rdx, rbp; pSid2
0x180014818  mov     rcx, rdi; pSid1
0x18001481b  call    cs:__imp_EqualSid
0x180014822  nop     dword ptr [rax+rax+00h]
0x180014827  xor     ebx, ebx
0x180014829  test    eax, eax
0x18001482b  setnz   bl
0x18001482e  jmp     short loc_18001485F
0x180014830  mov     rcx, cs:WPP_GLOBAL_Control
0x180014837  cmp     rcx, r15
0x18001483a  jz      short loc_18001485D
0x18001483c  test    [rcx+1Ch], r14d
0x180014840  jz      short loc_18001485D
0x180014842  cmp     byte ptr [rcx+19h], 2
0x180014846  jb      short loc_18001485D
0x180014848  mov     rcx, [rcx+10h]
0x18001484c  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180014853  mov     edx, 0B0h
0x180014858  call    WPP_SF_
0x18001485d  xor     ebx, ebx
0x18001485f  call    cs:__imp_RpcRevertToSelf
0x180014866  nop     dword ptr [rax+rax+00h]
0x18001486b  test    rdi, rdi
0x18001486e  jz      short loc_18001487F
0x180014870  mov     rcx, rdi; hMem
0x180014873  call    cs:__imp_LocalFree
0x18001487a  nop     dword ptr [rax+rax+00h]
0x18001487f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014886  cmp     rcx, r15
0x180014889  jz      short loc_1800148AF
0x18001488b  test    [rcx+1Ch], r14d
0x18001488f  jz      short loc_1800148AF
0x180014891  cmp     byte ptr [rcx+19h], 6
0x180014895  jb      short loc_1800148AF
0x180014897  mov     rcx, [rcx+10h]
0x18001489b  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x1800148a2  mov     r9b, bl
0x1800148a5  mov     edx, 0B1h
0x1800148aa  call    WPP_SF_c
0x1800148af  mov     eax, ebx
0x1800148b1  add     rsp, 28h
0x1800148b5  pop     r15
0x1800148b7  pop     r14
0x1800148b9  pop     rdi
0x1800148ba  pop     rsi
0x1800148bb  pop     rbp
0x1800148bc  pop     rbx
0x1800148bd  retn
```
