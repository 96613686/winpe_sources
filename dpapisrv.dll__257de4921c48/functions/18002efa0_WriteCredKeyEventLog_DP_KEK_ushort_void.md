# WriteCredKeyEventLog(DP_KEK *,ushort *,void *)

- ea: `0x18002efa0`
- end: `0x18002f118`
- name: `?WriteCredKeyEventLog@@YAXPEAUDP_KEK@@PEAGPEAX@Z`
- size: `376`
- prototype: `void(struct DP_KEK *, unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002e130`

## callees

- `0x18001d810`
- `0x18002efa0`
- `0x18002f15c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002f000`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002f000`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18002f07f`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18002f07f`
- `bcrypt!BCryptDestroyKey` at `0x18002f0e1`
- `bcrypt!BCryptDestroyKey` at `0x18002f0e1`
- `bcrypt!BCryptKeyDerivation` at `0x18002f0af`
- `bcrypt!BCryptKeyDerivation` at `0x18002f0af`

## pseudocode

```c
void __fastcall WriteCredKeyEventLog(struct DP_KEK *a1, unsigned __int16 *a2, void *a3)
{
  int v5; // r14d
  __int64 v6; // rbx
  __int64 pbSecret; // rax
  int v8; // edx
  int v9; // ecx
  _BYTE *v10; // rax
  int v11; // [rsp+40h] [rbp-49h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+48h] [rbp-41h] BYREF
  _DWORD v13[2]; // [rsp+50h] [rbp-39h] BYREF
  _DWORD *v14; // [rsp+58h] [rbp-31h]
  _DWORD v15[2]; // [rsp+60h] [rbp-29h] BYREF
  const char *v16; // [rsp+68h] [rbp-21h]
  DWORD LengthSid; // [rsp+70h] [rbp-19h]
  int v18; // [rsp+74h] [rbp-15h]
  void *v19; // [rsp+78h] [rbp-11h]
  __int64 v20; // [rsp+80h] [rbp-9h]
  const wchar_t *v21; // [rsp+88h] [rbp-1h]
  _OWORD v22[2]; // [rsp+90h] [rbp+7h] BYREF

  phKey = 0;
  v11 = 0;
  v15[0] = 20;
  v16 = "DPAPICredKeyLogging";
  memset(v22, 0, sizeof(v22));
  v5 = (int)a2;
  v15[1] = 13;
  v19 = a3;
  v6 = 32;
  LengthSid = GetLengthSid(a3);
  v18 = 14;
  v20 = 14;
  v21 = L"SHA256";
  v14 = v15;
  v13[0] = 0;
  v13[1] = 3;
  if ( a1 )
  {
    pbSecret = (__int64)a1 + 20;
    if ( a1 == (struct DP_KEK *)-20LL )
      pbSecret = 20;
    if ( BCryptGenerateSymmetricKey((BCRYPT_ALG_HANDLE)0x341, &phKey, 0, 0, (PUCHAR)pbSecret, 0x14u, 0) >= 0
      && (int)BCryptKeyDerivation(phKey, v13, v22, 32, &v11, 0) >= 0
      && (Microsoft_Windows_Crypto_DPAPIEnableBits & 0x20) != 0 )
    {
      McTemplateU0b32zk_EtwEventWriteTransfer(v9, v8, (unsigned int)v22, v5, (__int64)a3);
    }
  }
  if ( phKey )
    BCryptDestroyKey(phKey);
  v10 = v22;
  do
  {
    *v10++ = 0;
    --v6;
  }
  while ( v6 );
}

```

## disassembly

```asm
0x18002efa0  push    rbp
0x18002efa2  push    rbx
0x18002efa3  push    rsi
0x18002efa4  push    rdi
0x18002efa5  push    r14
0x18002efa7  lea     rbp, [rsp-37h]
0x18002efac  sub     rsp, 0C0h
0x18002efb3  mov     rax, cs:__security_cookie
0x18002efba  xor     rax, rsp
0x18002efbd  mov     [rbp+57h+var_30], rax
0x18002efc1  xorps   xmm0, xmm0
0x18002efc4  mov     [rbp+57h+phKey], 0
0x18002efcc  mov     rdi, rcx
0x18002efcf  mov     [rbp+57h+var_A0], 0
0x18002efd6  lea     rax, aDpapicredkeylo; "DPAPICredKeyLogging"
0x18002efdd  mov     [rbp+57h+var_80], 14h
0x18002efe4  mov     rcx, r8; pSid
0x18002efe7  mov     [rbp+57h+var_78], rax
0x18002efeb  movups  [rbp+57h+var_50], xmm0
0x18002efef  mov     rsi, r8
0x18002eff2  mov     r14, rdx
0x18002eff5  movups  [rbp+57h+var_40], xmm0
0x18002eff9  mov     [rbp+57h+var_7C], 0Dh
0x18002f000  call    cs:__imp_GetLengthSid
0x18002f007  nop     dword ptr [rax+rax+00h]
0x18002f00c  mov     [rbp+57h+var_68], rsi
0x18002f010  mov     ebx, 20h ; ' '
0x18002f015  mov     [rbp+57h+var_70], eax
0x18002f018  mov     eax, 0Eh
0x18002f01d  mov     [rbp+57h+var_6C], eax
0x18002f020  mov     [rbp+57h+var_60], rax
0x18002f024  lea     rax, aSha256; "SHA256"
0x18002f02b  mov     [rbp+57h+var_58], rax
0x18002f02f  lea     rax, [rbp+57h+var_80]
0x18002f033  mov     [rbp+57h+var_88], rax
0x18002f037  mov     [rbp+57h+var_90], 0
0x18002f03e  mov     [rbp+57h+var_8C], 3
0x18002f045  test    rdi, rdi
0x18002f048  jz      loc_18002F0D8
0x18002f04e  lea     rax, [rdi+14h]
0x18002f052  test    rax, rax
0x18002f055  jnz     short loc_18002F05B
0x18002f057  lea     rax, [rdi+28h]
0x18002f05b  mov     [rsp+0E0h+dwFlags], 0; dwFlags
0x18002f063  lea     rdx, [rbp+57h+phKey]; phKey
0x18002f067  mov     [rsp+0E0h+cbSecret], 14h; cbSecret
0x18002f06f  xor     r9d, r9d; cbKeyObject
0x18002f072  xor     r8d, r8d; pbKeyObject
0x18002f075  mov     [rsp+0E0h+pbSecret], rax; pbSecret
0x18002f07a  mov     ecx, 341h; hAlgorithm
0x18002f07f  call    cs:__imp_BCryptGenerateSymmetricKey
0x18002f086  nop     dword ptr [rax+rax+00h]
0x18002f08b  test    eax, eax
0x18002f08d  js      short loc_18002F0D8
0x18002f08f  mov     rcx, [rbp+57h+phKey]
0x18002f093  lea     rax, [rbp+57h+var_A0]
0x18002f097  mov     [rsp+0E0h+cbSecret], 0
0x18002f09f  lea     r8, [rbp+57h+var_50]
0x18002f0a3  mov     r9d, ebx
0x18002f0a6  mov     [rsp+0E0h+pbSecret], rax
0x18002f0ab  lea     rdx, [rbp+57h+var_90]
0x18002f0af  call    cs:__imp_BCryptKeyDerivation
0x18002f0b6  nop     dword ptr [rax+rax+00h]
0x18002f0bb  test    eax, eax
0x18002f0bd  js      short loc_18002F0D8
0x18002f0bf  test    cs:Microsoft_Windows_Crypto_DPAPIEnableBits, bl
0x18002f0c5  jz      short loc_18002F0D8
0x18002f0c7  mov     r9, r14
0x18002f0ca  mov     [rsp+0E0h+pbSecret], rsi
0x18002f0cf  lea     r8, [rbp+57h+var_50]
0x18002f0d3  call    McTemplateU0b32zk_EtwEventWriteTransfer
0x18002f0d8  mov     rcx, [rbp+57h+phKey]; hKey
0x18002f0dc  test    rcx, rcx
0x18002f0df  jz      short loc_18002F0ED
0x18002f0e1  call    cs:__imp_BCryptDestroyKey
0x18002f0e8  nop     dword ptr [rax+rax+00h]
0x18002f0ed  lea     rax, [rbp+57h+var_50]
0x18002f0f1  mov     byte ptr [rax], 0
0x18002f0f4  inc     rax
0x18002f0f7  sub     rbx, 1
0x18002f0fb  jnz     short loc_18002F0F1
0x18002f0fd  mov     rcx, [rbp+57h+var_30]
0x18002f101  xor     rcx, rsp; StackCookie
0x18002f104  call    __security_check_cookie
0x18002f109  add     rsp, 0C0h
0x18002f110  pop     r14
0x18002f112  pop     rdi
0x18002f113  pop     rsi
0x18002f114  pop     rbx
0x18002f115  pop     rbp
0x18002f116  retn
```
