# LPA::Lui::VerifyClientToken(LPA::Lui::LuiContextRecord const *,void *)

- ea: `0x1800ced10`
- end: `0x1800cedc8`
- name: `?VerifyClientToken@Lui@LPA@@CAJPEBVLuiContextRecord@12@PEAX@Z`
- size: `184`
- prototype: `static int(const struct LPA::Lui::LuiContextRecord *, void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c62d0`
- `0x1800cda00`

## callees

- `0x18000df90`
- `0x18000ebf4`
- `0x18006ba8c`
- `0x1800ced10`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800ced68`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800ced68`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800ced90`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800ced90`

## pseudocode

```c
__int64 __fastcall LPA::Lui::VerifyClientToken(const struct LPA::Lui::LuiContextRecord *a1, void *a2)
{
  __int64 result; // rax
  CommonUtil *v4; // rcx
  CommonUtil *v5; // rcx
  WINBOOL IsMember; // [rsp+20h] [rbp-78h] BYREF
  DWORD cbSid[3]; // [rsp+24h] [rbp-74h] BYREF
  _BYTE pSid[80]; // [rsp+30h] [rbp-68h] BYREF

  result = 0;
  if ( !*((_DWORD *)a1 + 4) )
  {
    if ( a2 )
    {
      memset_0(pSid, 0, 0x44u);
      cbSid[0] = 68;
      if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, cbSid)
        || (result = CommonUtil::GetLastErrorToHResultAndForceFailure(v4), (int)result >= 0) )
      {
        IsMember = 0;
        if ( CheckTokenMembership(a2, pSid, &IsMember) )
        {
          result = 0;
          if ( !IsMember )
            return 2147942405LL;
        }
        else
        {
          return CommonUtil::GetLastErrorToHResultAndForceFailure(v5);
        }
      }
    }
    else
    {
      return 2147942487LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800ced10  push    rbx
0x1800ced12  sub     rsp, 90h
0x1800ced19  mov     rax, cs:__security_cookie
0x1800ced20  xor     rax, rsp
0x1800ced23  mov     [rsp+98h+var_18], rax
0x1800ced2b  xor     eax, eax
0x1800ced2d  mov     rbx, rdx
0x1800ced30  cmp     [rcx+10h], eax
0x1800ced33  jnz     short loc_1800CEDAF
0x1800ced35  test    rdx, rdx
0x1800ced38  jnz     short loc_1800CED41
0x1800ced3a  mov     eax, 80070057h
0x1800ced3f  jmp     short loc_1800CEDAF
0x1800ced41  xor     edx, edx; Val
0x1800ced43  lea     rcx, [rsp+98h+pSid]; void *
0x1800ced48  lea     r8d, [rdx+44h]; Size
0x1800ced4c  call    memset_0
0x1800ced51  xor     edx, edx; DomainSid
0x1800ced53  mov     [rsp+98h+cbSid], 44h ; 'D'
0x1800ced5b  lea     r9, [rsp+98h+cbSid]; cbSid
0x1800ced60  lea     r8, [rsp+98h+pSid]; pSid
0x1800ced65  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x1800ced68  call    cs:__imp_CreateWellKnownSid
0x1800ced6e  test    eax, eax
0x1800ced70  jnz     short loc_1800CED7B
0x1800ced72  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800ced77  test    eax, eax
0x1800ced79  js      short loc_1800CEDAF
0x1800ced7b  lea     r8, [rsp+98h+IsMember]; IsMember
0x1800ced80  mov     [rsp+98h+IsMember], 0
0x1800ced88  lea     rdx, [rsp+98h+pSid]; SidToCheck
0x1800ced8d  mov     rcx, rbx; TokenHandle
0x1800ced90  call    cs:__imp_CheckTokenMembership
0x1800ced96  test    eax, eax
0x1800ced98  jnz     short loc_1800CEDA1
0x1800ced9a  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800ced9f  jmp     short loc_1800CEDAF
0x1800ceda1  xor     eax, eax
0x1800ceda3  mov     ecx, 80070005h
0x1800ceda8  cmp     [rsp+98h+IsMember], eax
0x1800cedac  cmovz   eax, ecx
0x1800cedaf  mov     rcx, [rsp+98h+var_18]
0x1800cedb7  xor     rcx, rsp; StackCookie
0x1800cedba  call    __security_check_cookie
0x1800cedbf  add     rsp, 90h
0x1800cedc6  pop     rbx
0x1800cedc7  retn
```
