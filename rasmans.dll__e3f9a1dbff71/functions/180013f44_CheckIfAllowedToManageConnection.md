# CheckIfAllowedToManageConnection

- ea: `0x180013f44`
- end: `0x1800140b3`
- name: `CheckIfAllowedToManageConnection`
- size: `367`
- prototype: `__int64 __fastcall(PSID pSid2, int, int)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019570`
- `0x180020dc0`
- `0x1800210fc`
- `0x1800314f0`

## callees

- `0x180005e0c`
- `0x18000bf70`
- `0x180013f44`
- `0x18003e660`
- `0x18004055c`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180013ff9`
- `RPCRT4!RpcImpersonateClient` at `0x180013ff9`
- `RPCRT4!RpcRevertToSelf` at `0x180014060`
- `RPCRT4!RpcRevertToSelf` at `0x180014060`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180014022`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180014022`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001406e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001406e`

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
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 174, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
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
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 176, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
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
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 175, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
LABEL_22:
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v8[1].Blink) & 0x2000) != 0
    && BYTE1(v8[1].Blink) >= 6u )
  {
    LOBYTE(v7) = v6;
    WPP_SF_c(v8[1].Flink, 177, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v7);
  }
  return v6;
}

```

## disassembly

```asm
0x180013f44  push    rbx
0x180013f46  push    rbp
0x180013f47  push    rsi
0x180013f48  push    rdi
0x180013f49  push    r14
0x180013f4b  push    r15
0x180013f4d  sub     rsp, 28h
0x180013f51  mov     edi, r8d
0x180013f54  mov     esi, edx
0x180013f56  mov     rbp, rcx
0x180013f59  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f60  lea     r15, WPP_GLOBAL_Control
0x180013f67  mov     r14d, 2000h
0x180013f6d  cmp     rcx, r15
0x180013f70  jz      short loc_180013F93
0x180013f72  test    [rcx+1Ch], r14d
0x180013f76  jz      short loc_180013F93
0x180013f78  cmp     byte ptr [rcx+19h], 6
0x180013f7c  jb      short loc_180013F93
0x180013f7e  mov     rcx, [rcx+10h]
0x180013f82  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180013f89  mov     edx, 0AEh
0x180013f8e  call    WPP_SF_
0x180013f93  neg     edi
0x180013f95  mov     [rsp+58h+pSid1], 0
0x180013f9e  mov     ebx, 1
0x180013fa3  sbb     ecx, ecx
0x180013fa5  and     ecx, 10h
0x180013fa8  add     ecx, 0Fh
0x180013fab  call    FRasmanAccessCheck
0x180013fb0  test    eax, eax
0x180013fb2  jnz     loc_180014074
0x180013fb8  test    esi, esi
0x180013fba  jz      short loc_180013FF7
0x180013fbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180013fc3  cmp     rcx, r15
0x180013fc6  jz      loc_1800140A4
0x180013fcc  test    [rcx+1Ch], r14d
0x180013fd0  jz      loc_18001407B
0x180013fd6  cmp     byte ptr [rcx+19h], 4
0x180013fda  jb      loc_18001407B
0x180013fe0  mov     rcx, [rcx+10h]
0x180013fe4  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180013feb  mov     edx, 0AFh
0x180013ff0  call    WPP_SF_
0x180013ff5  jmp     short loc_180014074
0x180013ff7  xor     ecx, ecx; BindingHandle
0x180013ff9  call    cs:__imp_RpcImpersonateClient
0x180013fff  test    eax, eax
0x180014001  jz      short loc_180014007
0x180014003  xor     ebx, ebx
0x180014005  jmp     short loc_180014074
0x180014007  lea     rdx, [rsp+58h+pSid1]
0x18001400c  xor     ecx, ecx
0x18001400e  call    GetUserSidFromToken
0x180014013  mov     rdi, [rsp+58h+pSid1]
0x180014018  test    eax, eax
0x18001401a  jnz     short loc_180014031
0x18001401c  mov     rdx, rbp; pSid2
0x18001401f  mov     rcx, rdi; pSid1
0x180014022  call    cs:__imp_EqualSid
0x180014028  xor     ebx, ebx
0x18001402a  test    eax, eax
0x18001402c  setnz   bl
0x18001402f  jmp     short loc_180014060
0x180014031  mov     rcx, cs:WPP_GLOBAL_Control
0x180014038  cmp     rcx, r15
0x18001403b  jz      short loc_18001405E
0x18001403d  test    [rcx+1Ch], r14d
0x180014041  jz      short loc_18001405E
0x180014043  cmp     byte ptr [rcx+19h], 2
0x180014047  jb      short loc_18001405E
0x180014049  mov     rcx, [rcx+10h]
0x18001404d  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180014054  mov     edx, 0B0h
0x180014059  call    WPP_SF_
0x18001405e  xor     ebx, ebx
0x180014060  call    cs:__imp_RpcRevertToSelf
0x180014066  test    rdi, rdi
0x180014069  jz      short loc_180014074
0x18001406b  mov     rcx, rdi; hMem
0x18001406e  call    cs:__imp_LocalFree
0x180014074  mov     rcx, cs:WPP_GLOBAL_Control
0x18001407b  cmp     rcx, r15
0x18001407e  jz      short loc_1800140A4
0x180014080  test    [rcx+1Ch], r14d
0x180014084  jz      short loc_1800140A4
0x180014086  cmp     byte ptr [rcx+19h], 6
0x18001408a  jb      short loc_1800140A4
0x18001408c  mov     rcx, [rcx+10h]
0x180014090  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180014097  mov     r9b, bl
0x18001409a  mov     edx, 0B1h
0x18001409f  call    WPP_SF_c
0x1800140a4  mov     eax, ebx
0x1800140a6  add     rsp, 28h
0x1800140aa  pop     r15
0x1800140ac  pop     r14
0x1800140ae  pop     rdi
0x1800140af  pop     rsi
0x1800140b0  pop     rbp
0x1800140b1  pop     rbx
0x1800140b2  retn
```
