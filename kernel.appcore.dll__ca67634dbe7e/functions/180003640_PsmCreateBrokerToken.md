# PsmCreateBrokerToken

- ea: `0x180003640`
- end: `0x1800038b8`
- name: `PsmCreateBrokerToken`
- size: `632`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003640`
- `0x1800038d0`
- `0x1800043b0`
- `0x180009dd0`

## import_xrefs

- `ntdll!NtClose` at `0x1800038a6`
- `ntdll!NtClose` at `0x1800038a6`
- `ntdll!RtlQueryPackageClaims` at `0x18000376d`
- `ntdll!RtlQueryPackageClaims` at `0x18000376d`
- `ntdll!NtDuplicateToken` at `0x18000370e`
- `ntdll!NtDuplicateToken` at `0x18000370e`

## string_xrefs

- `0x180003791`: `runtimebroker07f4358a809ac99a64a67c1`
- `0x180003895`: `Runtime Broker `

## pseudocode

```c
__int64 __fastcall PsmCreateBrokerToken(__int64 a1, void *a2, unsigned int a3, int a4, HANDLE *a5)
{
  char v5; // bl
  int v9; // ebp
  int v10; // edi
  int v11; // eax
  int v12; // edi
  UUID *v13; // rcx
  int v14; // edi
  HANDLE Handle; // [rsp+50h] [rbp-1E8h] BYREF
  __int64 v16; // [rsp+58h] [rbp-1E0h] BYREF
  __int64 v17; // [rsp+60h] [rbp-1D8h] BYREF
  __int64 v18; // [rsp+68h] [rbp-1D0h] BYREF
  wchar_t v19; // [rsp+70h] [rbp-1C8h] BYREF
  int v20[35]; // [rsp+72h] [rbp-1C6h] BYREF
  WCHAR v21[128]; // [rsp+100h] [rbp-138h] BYREF

  v17 = 0;
  v5 = a4;
  v18 = 0;
  v16 = 0;
  Handle = 0;
  if ( a3 > 1 )
    return 3221225713LL;
  if ( (a4 & 0xFFFFFFF0) != 0 )
    return 3221225714LL;
  v9 = a4 & 8;
  if ( (a4 & 8) != 0 && (a4 & 4) != 0 )
    return 3221225714LL;
  if ( (a4 & 2) == 0 && !NtCurrentTeb()->IsImpersonating )
    return 3221225564LL;
  v10 = NtDuplicateToken(a2, 0, 0, 0, TokenPrimary, &Handle);
  if ( v10 >= 0 )
  {
    v17 = 130;
    v19 = 33;
    v18 = 256;
    v11 = RtlQueryPackageClaims(a1, v21, &v18, v20, &v17, 0, &v16, 0);
    v10 = v11;
    if ( v11 < 0 )
    {
      if ( v11 == -1073741275 )
      {
LABEL_16:
        *a5 = Handle;
        return 0;
      }
      goto LABEL_20;
    }
    if ( (v5 & 1) != 0 )
      v12 = 0;
    else
      v12 = v16;
    if ( !a3 )
    {
      RtlStringCbPrintfExW((int)v20, 130, 0, 0, 2048, (__int64)L"%s", (char)L"runtimebroker07f4358a809ac99a64a67c1");
      v13 = 0;
      goto LABEL_13;
    }
    if ( a3 == 1 )
    {
      v13 = (UUID *)"Runtime Broker ";
      v12 |= 0x40000000u;
LABEL_13:
      v14 = v12 | 0x40;
      if ( v9 )
      {
        v14 |= 0x100u;
      }
      else if ( (v5 & 4) != 0 )
      {
        v14 |= 0x80u;
      }
      v10 = PsmpAdjustActivationToken(Handle, v14 | 0x80000000, 0, v21, &v19, (PackageOrigin)BYTE4(v16), v13, 0, 0, 0);
      if ( v10 >= 0 )
        goto LABEL_16;
      goto LABEL_20;
    }
    v10 = -1073741583;
  }
LABEL_20:
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180003640  mov     [rsp+arg_18], rbx
0x180003645  push    rsi
0x180003646  push    rdi
0x180003647  push    r12
0x180003649  push    r14
0x18000364b  push    r15
0x18000364d  sub     rsp, 210h
0x180003654  mov     rax, cs:__security_cookie
0x18000365b  xor     rax, rsp
0x18000365e  mov     [rsp+238h+var_38], rax
0x180003666  mov     r14, [rsp+238h+arg_20]
0x18000366e  xor     r12d, r12d
0x180003671  mov     [rsp+238h+var_1D8], r12
0x180003676  mov     ebx, r9d
0x180003679  mov     [rsp+238h+var_1D0], r12
0x18000367e  mov     esi, r8d
0x180003681  mov     [rsp+238h+var_1E0], r12
0x180003686  mov     r10, rdx
0x180003689  mov     [rsp+238h+Handle], r12
0x18000368e  mov     r15, rcx
0x180003691  cmp     r8d, 1
0x180003695  ja      loc_1800038AE
0x18000369b  test    ebx, 0FFFFFFF0h
0x1800036a1  jz      short loc_1800036D0
0x1800036a3  mov     eax, 0C00000F2h
0x1800036a8  mov     rcx, [rsp+238h+var_38]
0x1800036b0  xor     rcx, rsp; StackCookie
0x1800036b3  call    __security_check_cookie
0x1800036b8  mov     rbx, [rsp+238h+arg_18]
0x1800036c0  add     rsp, 210h
0x1800036c7  pop     r15
0x1800036c9  pop     r14
0x1800036cb  pop     r12
0x1800036cd  pop     rdi
0x1800036ce  pop     rsi
0x1800036cf  retn
0x1800036d0  mov     [rsp+238h+arg_10], rbp
0x1800036d8  mov     ebp, ebx
0x1800036da  and     ebp, 8
0x1800036dd  jz      short loc_1800036E8
0x1800036df  test    bl, 4
0x1800036e2  jnz     loc_18000386B
0x1800036e8  test    bl, 2
0x1800036eb  jz      loc_180003872
0x1800036f1  lea     rax, [rsp+238h+Handle]
0x1800036f6  xor     r9d, r9d; EffectiveOnly
0x1800036f9  mov     [rsp+238h+NewTokenHandle], rax; NewTokenHandle
0x1800036fe  xor     r8d, r8d; ObjectAttributes
0x180003701  xor     edx, edx; DesiredAccess
0x180003703  mov     [rsp+238h+TokenType], 1; TokenType
0x18000370b  mov     rcx, r10; ExistingTokenHandle
0x18000370e  call    cs:__imp_NtDuplicateToken
0x180003714  mov     edi, eax
0x180003716  test    eax, eax
0x180003718  js      loc_180003849
0x18000371e  mov     [rsp+238h+var_200], r12
0x180003723  lea     r9, [rsp+238h+var_1C6]
0x180003728  mov     eax, 21h ; '!'
0x18000372d  mov     [rsp+238h+var_1D8], 82h
0x180003736  mov     [rsp+238h+var_1C8], ax
0x18000373b  lea     r8, [rsp+238h+var_1D0]
0x180003740  lea     rax, [rsp+238h+var_1E0]
0x180003745  mov     [rsp+238h+var_1D0], 100h
0x18000374e  mov     qword ptr [rsp+238h+Args], rax
0x180003753  lea     rdx, [rsp+238h+var_138]
0x18000375b  lea     rax, [rsp+238h+var_1D8]
0x180003760  mov     [rsp+238h+NewTokenHandle], r12
0x180003765  mov     rcx, r15
0x180003768  mov     qword ptr [rsp+238h+TokenType], rax
0x18000376d  call    cs:__imp_RtlQueryPackageClaims
0x180003773  mov     edi, eax
0x180003775  test    eax, eax
0x180003777  js      loc_180003842
0x18000377d  test    bl, 1
0x180003780  jz      loc_180003862
0x180003786  mov     rdi, r12
0x180003789  test    esi, esi
0x18000378b  jnz     loc_180003889
0x180003791  lea     rax, Args; "runtimebroker07f4358a809ac99a64a67c1"
0x180003798  xor     r9d, r9d; int
0x18000379b  mov     qword ptr [rsp+238h+Args], rax; Args
0x1800037a0  lea     rcx, [rsp+238h+var_1C6]; int
0x1800037a5  lea     rax, aS; "%s"
0x1800037ac  xor     r8d, r8d; int
0x1800037af  mov     [rsp+238h+NewTokenHandle], rax; __int64
0x1800037b4  mov     edx, 82h; int
0x1800037b9  mov     [rsp+238h+TokenType], 800h; int
0x1800037c1  call    RtlStringCbPrintfExW
0x1800037c6  mov     rcx, r12
0x1800037c9  or      rdi, 40h
0x1800037cd  test    ebp, ebp
0x1800037cf  jz      short loc_180003836
0x1800037d1  bts     rdi, 8
0x1800037d6  movzx   eax, byte ptr [rsp+238h+var_1E0+4]
0x1800037db  lea     r9, [rsp+238h+var_138]
0x1800037e3  mov     [rsp+238h+var_1F0], r12
0x1800037e8  bts     edi, 1Fh
0x1800037ec  mov     [rsp+238h+var_1F8], r12
0x1800037f1  xor     r8d, r8d
0x1800037f4  mov     [rsp+238h+var_200], r12
0x1800037f9  mov     edx, edi
0x1800037fb  mov     qword ptr [rsp+238h+Args], rcx
0x180003800  mov     rcx, [rsp+238h+Handle]
0x180003805  mov     dword ptr [rsp+238h+NewTokenHandle], eax
0x180003809  lea     rax, [rsp+238h+var_1C8]
0x18000380e  mov     qword ptr [rsp+238h+TokenType], rax
0x180003813  call    PsmpAdjustActivationToken
0x180003818  mov     edi, eax
0x18000381a  test    eax, eax
0x18000381c  js      short loc_180003849
0x18000381e  mov     rax, [rsp+238h+Handle]
0x180003823  mov     [r14], rax
0x180003826  mov     eax, r12d
0x180003829  mov     rbp, [rsp+238h+arg_10]
0x180003831  jmp     loc_1800036A8
0x180003836  test    bl, 4
0x180003839  jz      short loc_1800037D6
0x18000383b  bts     rdi, 7
0x180003840  jmp     short loc_1800037D6
0x180003842  cmp     eax, 0C0000225h
0x180003847  jz      short loc_18000381E
0x180003849  mov     rcx, [rsp+238h+Handle]; Handle
0x18000384e  test    rcx, rcx
0x180003851  jnz     short loc_1800038A6
0x180003853  mov     rbp, [rsp+238h+arg_10]
0x18000385b  mov     eax, edi
0x18000385d  jmp     loc_1800036A8
0x180003862  mov     edi, dword ptr [rsp+238h+var_1E0]
0x180003866  jmp     loc_180003789
0x18000386b  mov     eax, 0C00000F2h
0x180003870  jmp     short loc_180003829
0x180003872  mov     eax, gs:179Ch
0x18000387a  test    eax, eax
0x18000387c  jnz     loc_1800036F1
0x180003882  mov     eax, 0C000005Ch
0x180003887  jmp     short loc_180003829
0x180003889  cmp     esi, 1
0x18000388c  jz      short loc_180003895
0x18000388e  mov     edi, 0C00000F1h
0x180003893  jmp     short loc_180003849
0x180003895  lea     rcx, PsmpBrokerDynamicId; "Runtime Broker "
0x18000389c  bts     rdi, 1Eh
0x1800038a1  jmp     loc_1800037C9
0x1800038a6  call    cs:__imp_NtClose
0x1800038ac  jmp     short loc_180003853
0x1800038ae  mov     eax, 0C00000F1h
0x1800038b3  jmp     loc_1800036A8
```
