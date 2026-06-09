# CSecuritySession::fIsValidTrusteeForm(_TRUSTEE_W *)

- ea: `0x10044090`
- end: `0x100440c8`
- name: `?fIsValidTrusteeForm@CSecuritySession@@QBEHPAU_TRUSTEE_W@@@Z`
- size: `56`
- prototype: `int __thiscall(CSecuritySession *__hidden this, struct _TRUSTEE_W *)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10040610`
- `0x10041060`
- `0x10041210`
- `0x100413c0`
- `0x10041890`
- `0x10041f50`
- `0x10042c60`
- `0x10043310`

## callees

- `0x10044090`

## pseudocode

```c
BOOL __thiscall CSecuritySession::fIsValidTrusteeForm(CSecuritySession *this, struct _TRUSTEE_W *a2)
{
  TRUSTEE_TYPE TrusteeType; // eax

  if ( !a2->pMultipleTrustee
    && a2->MultipleTrusteeOperation == NO_MULTIPLE_TRUSTEE
    && ((TrusteeType = a2->TrusteeType, TrusteeType == TRUSTEE_IS_USER) || TrusteeType == TRUSTEE_IS_GROUP)
    && a2->TrusteeForm == TRUSTEE_IS_NAME )
  {
    return a2->ptstrName != 0;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x10044090  mov     edi, edi
0x10044092  push    ebp
0x10044093  mov     ebp, esp
0x10044095  mov     ecx, [ebp+arg_0]
0x10044098  cmp     dword ptr [ecx], 0
0x1004409b  jnz     short loc_100440C2
0x1004409d  cmp     dword ptr [ecx+4], 0
0x100440a1  jnz     short loc_100440C2
0x100440a3  mov     eax, [ecx+0Ch]
0x100440a6  cmp     eax, 1
0x100440a9  jz      short loc_100440B0
0x100440ab  cmp     eax, 2
0x100440ae  jnz     short loc_100440C2
0x100440b0  cmp     dword ptr [ecx+8], 1
0x100440b4  jnz     short loc_100440C2
0x100440b6  xor     eax, eax
0x100440b8  cmp     [ecx+10h], eax
0x100440bb  setnz   al
0x100440be  pop     ebp
0x100440bf  retn    4
0x100440c2  xor     eax, eax
0x100440c4  pop     ebp
0x100440c5  retn    4
```
