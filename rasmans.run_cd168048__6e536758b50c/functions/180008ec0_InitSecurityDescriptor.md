# InitSecurityDescriptor

- ea: `0x180008ec0`
- end: `0x180009343`
- name: `InitSecurityDescriptor`
- size: `1155`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800073ac`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x180008ec0`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009055`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000911b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000917d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800091e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000923c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009287`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009055`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000911b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000917d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800091e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000923c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009287`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180009027`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180009027`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18000922c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18000922c`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000910b`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000910b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180009277`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180009277`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180009012`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180009012`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180008f27`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180008f27`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000916d`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000916d`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180008fab`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180008fab`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800090a3`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800090a3`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800091d1`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800091d1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008f3a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000903d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008f3a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000903d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800092bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800092e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800092bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800092e5`

## pseudocode

```c
__int64 InitSecurityDescriptor()
{
  DWORD SidLengthRequired; // eax
  HLOCAL v1; // rax
  void *v2; // rdi
  DWORD v3; // eax
  DWORD v4; // ebx
  struct _LIST_ENTRY *v5; // rcx
  DWORD LastError; // eax
  struct _LIST_ENTRY *v7; // rcx
  __int64 v8; // rdx
  DWORD v9; // ebx
  struct _ACL *v10; // rax
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+20h] [rbp-38h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 213, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids);
  }
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 256;
  SidLengthRequired = GetSidLengthRequired(1u);
  v1 = LocalAlloc(0x40u, SidLengthRequired);
  v2 = v1;
  if ( v1 )
  {
    if ( InitializeSid(v1, &pIdentifierAuthority, 1u) )
    {
      *GetSidSubAuthority(v2, 0) = 0;
      v9 = GetLengthSid(v2) + 20;
      v10 = (struct _ACL *)LocalAlloc(0x40u, v9);
      g_pDacl = v10;
      if ( v10 )
      {
        if ( InitializeAcl(v10, v9, 2u) )
        {
          if ( AddAccessAllowedAce(g_pDacl, 2u, 0x12FFFFu, v2) )
          {
            if ( InitializeSecurityDescriptor(RasmanSecurityDescriptor, 1u) )
            {
              if ( SetSecurityDescriptorDacl(RasmanSecurityDescriptor, 1, g_pDacl, 0) )
              {
                if ( SetSecurityDescriptorOwner(RasmanSecurityDescriptor, 0, 0) )
                {
                  if ( SetSecurityDescriptorGroup(RasmanSecurityDescriptor, 0, 0) )
                  {
                    v4 = 0;
                  }
                  else
                  {
                    LastError = GetLastError();
                    v4 = LastError;
                    if ( LastError )
                    {
                      v7 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                      {
                        v8 = 222;
                        goto LABEL_17;
                      }
                    }
                  }
                }
                else
                {
                  LastError = GetLastError();
                  v4 = LastError;
                  if ( LastError )
                  {
                    v7 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                    {
                      v8 = 221;
                      goto LABEL_17;
                    }
                  }
                }
              }
              else
              {
                LastError = GetLastError();
                v4 = LastError;
                if ( LastError )
                {
                  v7 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                  {
                    v8 = 220;
                    goto LABEL_17;
                  }
                }
              }
            }
            else
            {
              LastError = GetLastError();
              v4 = LastError;
              if ( LastError )
              {
                v7 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                  && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  v8 = 219;
                  goto LABEL_17;
                }
              }
            }
          }
          else
          {
            LastError = GetLastError();
            v4 = LastError;
            if ( LastError )
            {
              v7 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                v8 = 218;
                goto LABEL_17;
              }
            }
          }
        }
        else
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError )
          {
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v8 = 217;
              goto LABEL_17;
            }
          }
        }
      }
      else
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError )
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            v8 = 216;
            goto LABEL_17;
          }
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          v8 = 215;
LABEL_17:
          WPP_SF_d(v7[1].Flink, v8, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids, LastError);
        }
      }
    }
    LocalFree(v2);
    if ( v4 )
      goto LABEL_62;
LABEL_65:
    v5 = WPP_GLOBAL_Control;
    goto LABEL_66;
  }
  v3 = GetLastError();
  v4 = v3;
  if ( !v3 )
    goto LABEL_65;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 214, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids, v3);
LABEL_62:
    v5 = WPP_GLOBAL_Control;
  }
  if ( g_pDacl )
  {
    LocalFree(g_pDacl);
    g_pDacl = 0;
    goto LABEL_65;
  }
LABEL_66:
  if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v5[1].Blink) & 0x2000) != 0
    && BYTE1(v5[1].Blink) >= 6u )
  {
    WPP_SF_d(v5[1].Flink, 223, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x180008ec0  push    rbx
0x180008ec2  push    rbp
0x180008ec3  push    rdi
0x180008ec4  push    r14
0x180008ec6  push    r15
0x180008ec8  sub     rsp, 30h
0x180008ecc  mov     rax, cs:__security_cookie
0x180008ed3  xor     rax, rsp
0x180008ed6  mov     [rsp+58h+var_30], rax
0x180008edb  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ee2  lea     r14, WPP_GLOBAL_Control
0x180008ee9  lea     r15, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids
0x180008ef0  mov     ebp, 2000h
0x180008ef5  cmp     rcx, r14
0x180008ef8  jz      short loc_180008F16
0x180008efa  test    [rcx+1Ch], ebp
0x180008efd  jz      short loc_180008F16
0x180008eff  cmp     byte ptr [rcx+19h], 6
0x180008f03  jb      short loc_180008F16
0x180008f05  mov     rcx, [rcx+10h]
0x180008f09  mov     edx, 0D5h
0x180008f0e  mov     r8, r15
0x180008f11  call    WPP_SF_
0x180008f16  mov     cl, 1; nSubAuthorityCount
0x180008f18  mov     dword ptr [rsp+58h+pIdentifierAuthority.Value], 0
0x180008f20  mov     word ptr [rsp+58h+pIdentifierAuthority.Value+4], 100h
0x180008f27  call    cs:__imp_GetSidLengthRequired
0x180008f2e  nop     dword ptr [rax+rax+00h]
0x180008f33  mov     edx, eax; uBytes
0x180008f35  mov     ecx, 40h ; '@'; uFlags
0x180008f3a  call    cs:__imp_LocalAlloc
0x180008f41  nop     dword ptr [rax+rax+00h]
0x180008f46  mov     rdi, rax
0x180008f49  test    rax, rax
0x180008f4c  jnz     short loc_180008FA0
0x180008f4e  call    cs:__imp_GetLastError
0x180008f55  nop     dword ptr [rax+rax+00h]
0x180008f5a  mov     ebx, eax
0x180008f5c  test    eax, eax
0x180008f5e  jz      loc_1800092FC
0x180008f64  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f6b  cmp     rcx, r14
0x180008f6e  jz      loc_1800092D6
0x180008f74  test    [rcx+1Ch], ebp
0x180008f77  jz      loc_1800092D6
0x180008f7d  cmp     byte ptr [rcx+19h], 2
0x180008f81  jb      loc_1800092D6
0x180008f87  mov     rcx, [rcx+10h]
0x180008f8b  mov     edx, 0D6h
0x180008f90  mov     r9d, eax
0x180008f93  mov     r8, r15
0x180008f96  call    WPP_SF_d
0x180008f9b  jmp     loc_1800092CF
0x180008fa0  mov     r8b, 1; nSubAuthorityCount
0x180008fa3  lea     rdx, [rsp+58h+pIdentifierAuthority]; pIdentifierAuthority
0x180008fa8  mov     rcx, rdi; Sid
0x180008fab  call    cs:__imp_InitializeSid
0x180008fb2  nop     dword ptr [rax+rax+00h]
0x180008fb7  test    eax, eax
0x180008fb9  jnz     short loc_18000900D
0x180008fbb  call    cs:__imp_GetLastError
0x180008fc2  nop     dword ptr [rax+rax+00h]
0x180008fc7  mov     ebx, eax
0x180008fc9  test    eax, eax
0x180008fcb  jz      loc_1800092BC
0x180008fd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180008fd8  cmp     rcx, r14
0x180008fdb  jz      loc_1800092BC
0x180008fe1  test    [rcx+1Ch], ebp
0x180008fe4  jz      loc_1800092BC
0x180008fea  cmp     byte ptr [rcx+19h], 2
0x180008fee  jb      loc_1800092BC
0x180008ff4  mov     edx, 0D7h
0x180008ff9  mov     rcx, [rcx+10h]
0x180008ffd  mov     r9d, eax
0x180009000  mov     r8, r15
0x180009003  call    WPP_SF_d
0x180009008  jmp     loc_1800092BC
0x18000900d  xor     edx, edx; nSubAuthority
0x18000900f  mov     rcx, rdi; pSid
0x180009012  call    cs:__imp_GetSidSubAuthority
0x180009019  nop     dword ptr [rax+rax+00h]
0x18000901e  mov     rcx, rdi; pSid
0x180009021  mov     dword ptr [rax], 0
0x180009027  call    cs:__imp_GetLengthSid
0x18000902e  nop     dword ptr [rax+rax+00h]
0x180009033  mov     ecx, 40h ; '@'; uFlags
0x180009038  lea     ebx, [rax+14h]
0x18000903b  mov     edx, ebx; uBytes
0x18000903d  call    cs:__imp_LocalAlloc
0x180009044  nop     dword ptr [rax+rax+00h]
0x180009049  mov     cs:g_pDacl, rax
0x180009050  test    rax, rax
0x180009053  jnz     short loc_180009098
0x180009055  call    cs:__imp_GetLastError
0x18000905c  nop     dword ptr [rax+rax+00h]
0x180009061  mov     ebx, eax
0x180009063  test    eax, eax
0x180009065  jz      loc_1800092BC
0x18000906b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009072  cmp     rcx, r14
0x180009075  jz      loc_1800092BC
0x18000907b  test    [rcx+1Ch], ebp
0x18000907e  jz      loc_1800092BC
0x180009084  cmp     byte ptr [rcx+19h], 2
0x180009088  jb      loc_1800092BC
0x18000908e  mov     edx, 0D8h
0x180009093  jmp     loc_180008FF9
0x180009098  mov     r8d, 2; dwAclRevision
0x18000909e  mov     edx, ebx; nAclLength
0x1800090a0  mov     rcx, rax; pAcl
0x1800090a3  call    cs:__imp_InitializeAcl
0x1800090aa  nop     dword ptr [rax+rax+00h]
0x1800090af  test    eax, eax
0x1800090b1  jnz     short loc_1800090F6
0x1800090b3  call    cs:__imp_GetLastError
0x1800090ba  nop     dword ptr [rax+rax+00h]
0x1800090bf  mov     ebx, eax
0x1800090c1  test    eax, eax
0x1800090c3  jz      loc_1800092BC
0x1800090c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090d0  cmp     rcx, r14
0x1800090d3  jz      loc_1800092BC
0x1800090d9  test    [rcx+1Ch], ebp
0x1800090dc  jz      loc_1800092BC
0x1800090e2  cmp     byte ptr [rcx+19h], 2
0x1800090e6  jb      loc_1800092BC
0x1800090ec  mov     edx, 0D9h
0x1800090f1  jmp     loc_180008FF9
0x1800090f6  mov     rcx, cs:g_pDacl; pAcl
0x1800090fd  mov     r9, rdi; pSid
0x180009100  mov     edx, 2; dwAceRevision
0x180009105  mov     r8d, 12FFFFh; AccessMask
0x18000910b  call    cs:__imp_AddAccessAllowedAce
0x180009112  nop     dword ptr [rax+rax+00h]
0x180009117  test    eax, eax
0x180009119  jnz     short loc_18000915E
0x18000911b  call    cs:__imp_GetLastError
0x180009122  nop     dword ptr [rax+rax+00h]
0x180009127  mov     ebx, eax
0x180009129  test    eax, eax
0x18000912b  jz      loc_1800092BC
0x180009131  mov     rcx, cs:WPP_GLOBAL_Control
0x180009138  cmp     rcx, r14
0x18000913b  jz      loc_1800092BC
0x180009141  test    [rcx+1Ch], ebp
0x180009144  jz      loc_1800092BC
0x18000914a  cmp     byte ptr [rcx+19h], 2
0x18000914e  jb      loc_1800092BC
0x180009154  mov     edx, 0DAh
0x180009159  jmp     loc_180008FF9
0x18000915e  lea     rbx, RasmanSecurityDescriptor
0x180009165  mov     edx, 1; dwRevision
0x18000916a  mov     rcx, rbx; pSecurityDescriptor
0x18000916d  call    cs:__imp_InitializeSecurityDescriptor
0x180009174  nop     dword ptr [rax+rax+00h]
0x180009179  test    eax, eax
0x18000917b  jnz     short loc_1800091C0
0x18000917d  call    cs:__imp_GetLastError
0x180009184  nop     dword ptr [rax+rax+00h]
0x180009189  mov     ebx, eax
0x18000918b  test    eax, eax
0x18000918d  jz      loc_1800092BC
0x180009193  mov     rcx, cs:WPP_GLOBAL_Control
0x18000919a  cmp     rcx, r14
0x18000919d  jz      loc_1800092BC
0x1800091a3  test    [rcx+1Ch], ebp
0x1800091a6  jz      loc_1800092BC
0x1800091ac  cmp     byte ptr [rcx+19h], 2
0x1800091b0  jb      loc_1800092BC
0x1800091b6  mov     edx, 0DBh
0x1800091bb  jmp     loc_180008FF9
0x1800091c0  mov     r8, cs:g_pDacl; pDacl
0x1800091c7  xor     r9d, r9d; bDaclDefaulted
0x1800091ca  mov     rcx, rbx; pSecurityDescriptor
0x1800091cd  lea     edx, [r9+1]; bDaclPresent
0x1800091d1  call    cs:__imp_SetSecurityDescriptorDacl
0x1800091d8  nop     dword ptr [rax+rax+00h]
0x1800091dd  test    eax, eax
0x1800091df  jnz     short loc_180009224
0x1800091e1  call    cs:__imp_GetLastError
0x1800091e8  nop     dword ptr [rax+rax+00h]
0x1800091ed  mov     ebx, eax
0x1800091ef  test    eax, eax
0x1800091f1  jz      loc_1800092BC
0x1800091f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091fe  cmp     rcx, r14
0x180009201  jz      loc_1800092BC
0x180009207  test    [rcx+1Ch], ebp
0x18000920a  jz      loc_1800092BC
0x180009210  cmp     byte ptr [rcx+19h], 2
0x180009214  jb      loc_1800092BC
0x18000921a  mov     edx, 0DCh
0x18000921f  jmp     loc_180008FF9
0x180009224  xor     r8d, r8d; bOwnerDefaulted
0x180009227  xor     edx, edx; pOwner
0x180009229  mov     rcx, rbx; pSecurityDescriptor
0x18000922c  call    cs:__imp_SetSecurityDescriptorOwner
0x180009233  nop     dword ptr [rax+rax+00h]
0x180009238  test    eax, eax
0x18000923a  jnz     short loc_18000926F
0x18000923c  call    cs:__imp_GetLastError
0x180009243  nop     dword ptr [rax+rax+00h]
0x180009248  mov     ebx, eax
0x18000924a  test    eax, eax
0x18000924c  jz      short loc_1800092BC
0x18000924e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009255  cmp     rcx, r14
0x180009258  jz      short loc_1800092BC
0x18000925a  test    [rcx+1Ch], ebp
0x18000925d  jz      short loc_1800092BC
0x18000925f  cmp     byte ptr [rcx+19h], 2
0x180009263  jb      short loc_1800092BC
0x180009265  mov     edx, 0DDh
0x18000926a  jmp     loc_180008FF9
0x18000926f  xor     r8d, r8d; bGroupDefaulted
0x180009272  xor     edx, edx; pGroup
0x180009274  mov     rcx, rbx; pSecurityDescriptor
0x180009277  call    cs:__imp_SetSecurityDescriptorGroup
0x18000927e  nop     dword ptr [rax+rax+00h]
0x180009283  test    eax, eax
0x180009285  jnz     short loc_1800092BA
0x180009287  call    cs:__imp_GetLastError
0x18000928e  nop     dword ptr [rax+rax+00h]
0x180009293  mov     ebx, eax
0x180009295  test    eax, eax
0x180009297  jz      short loc_1800092BC
0x180009299  mov     rcx, cs:WPP_GLOBAL_Control
0x1800092a0  cmp     rcx, r14
0x1800092a3  jz      short loc_1800092BC
0x1800092a5  test    [rcx+1Ch], ebp
0x1800092a8  jz      short loc_1800092BC
0x1800092aa  cmp     byte ptr [rcx+19h], 2
0x1800092ae  jb      short loc_1800092BC
0x1800092b0  mov     edx, 0DEh
0x1800092b5  jmp     loc_180008FF9
0x1800092ba  xor     ebx, ebx
0x1800092bc  mov     rcx, rdi; hMem
0x1800092bf  call    cs:__imp_LocalFree
0x1800092c6  nop     dword ptr [rax+rax+00h]
0x1800092cb  test    ebx, ebx
0x1800092cd  jz      short loc_1800092FC
0x1800092cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800092d6  mov     rax, cs:g_pDacl
0x1800092dd  test    rax, rax
0x1800092e0  jz      short loc_180009303
0x1800092e2  mov     rcx, rax; hMem
0x1800092e5  call    cs:__imp_LocalFree
0x1800092ec  nop     dword ptr [rax+rax+00h]
0x1800092f1  mov     cs:g_pDacl, 0
0x1800092fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180009303  cmp     rcx, r14
0x180009306  jz      short loc_180009327
0x180009308  test    [rcx+1Ch], ebp
0x18000930b  jz      short loc_180009327
0x18000930d  cmp     byte ptr [rcx+19h], 6
0x180009311  jb      short loc_180009327
0x180009313  mov     rcx, [rcx+10h]
0x180009317  mov     edx, 0DFh
0x18000931c  mov     r9d, ebx
0x18000931f  mov     r8, r15
0x180009322  call    WPP_SF_d
0x180009327  mov     eax, ebx
0x180009329  mov     rcx, [rsp+58h+var_30]
0x18000932e  xor     rcx, rsp; StackCookie
0x180009331  call    __security_check_cookie
0x180009336  add     rsp, 30h
0x18000933a  pop     r15
0x18000933c  pop     r14
0x18000933e  pop     rdi
0x18000933f  pop     rbp
0x180009340  pop     rbx
0x180009341  retn
```
