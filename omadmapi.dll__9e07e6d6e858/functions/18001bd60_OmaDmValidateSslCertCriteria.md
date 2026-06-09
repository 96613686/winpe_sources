# OmaDmValidateSslCertCriteria

- ea: `0x18001bd60`
- end: `0x18001bfd2`
- name: `OmaDmValidateSslCertCriteria`
- size: `626`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18001bd60`
- `0x180024010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001be76`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001beea`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001be76`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001beea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bf85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bf85`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001bdea`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001bdea`
- `OLEAUT32!__imp_SysFreeString` at `0x18001bf96`
- `OLEAUT32!__imp_SysFreeString` at `0x18001bf96`
- `DMCmnUtils!BigStrcat` at `0x18001bdae`
- `DMCmnUtils!BigStrcat` at `0x18001bdae`
- `DMCmnUtils!InvStrCmpNIW` at `0x18001bf1d`
- `DMCmnUtils!InvStrCmpNIW` at `0x18001bf55`
- `DMCmnUtils!InvStrCmpNIW` at `0x18001bf1d`
- `DMCmnUtils!InvStrCmpNIW` at `0x18001bf55`

## pseudocode

```c
__int64 __fastcall OmaDmValidateSslCertCriteria(__int64 a1, _DWORD *a2)
{
  unsigned __int16 *v3; // r15
  HRESULT v4; // ebx
  int v5; // eax
  HRESULT v6; // eax
  wchar_t *v7; // rdi
  wchar_t *v8; // rax
  wchar_t *v9; // rsi
  __int64 v10; // rdx
  wchar_t *v11; // rax
  wchar_t *v12; // rax
  const unsigned __int16 *v13; // rbp
  unsigned __int64 v14; // r8
  const unsigned __int16 *v15; // rdx
  LPVOID ppv; // [rsp+60h] [rbp+8h] BYREF
  wchar_t *Str; // [rsp+70h] [rbp+18h] BYREF

  ppv = 0;
  v3 = 0;
  Str = 0;
  if ( !a1 || !a2 )
  {
    v4 = -2147467261;
    goto LABEL_34;
  }
  *a2 = 0;
  v3 = BigStrcat(2u, L".?", a1);
  if ( !v3 )
  {
    v4 = -2147024882;
    goto LABEL_34;
  }
  v4 = CoCreateInstance(
         &GUID_50a41ef1_6bfa_4b7e_973e_798ea0bebad4,
         0,
         1u,
         &GUID_e34e5896_40b2_45c4_a9c0_8a9601c3b0a6,
         &ppv);
  if ( v4 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *))(*(_QWORD *)ppv + 40LL))(ppv, v3);
    v4 = v5;
    if ( v5 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, wchar_t **))(*(_QWORD *)ppv + 128LL))(
             ppv,
             L"Stores",
             &Str);
      v4 = 0;
      if ( v6 != -2147023728 )
        v4 = v6;
      if ( v4 >= 0 )
      {
        v7 = Str;
        if ( Str )
        {
          while ( 1 )
          {
            v8 = wcschr(v7, 0xF000u);
            v9 = v8;
            if ( v8 )
            {
              *v8 = 0;
            }
            else
            {
              if ( !v7 )
              {
                v4 = -2147024809;
                goto LABEL_34;
              }
              v10 = 0x7FFFFFFF;
              v11 = v7;
              do
              {
                if ( !*v11 )
                  break;
                ++v11;
                --v10;
              }
              while ( v10 );
              v4 = v10 == 0 ? 0x80070057 : 0;
              if ( !v10 )
                goto LABEL_34;
              v9 = &v7[(0x7FFFFFFF - v10) & -(__int64)(v10 != 0)];
            }
            v12 = wcschr(v7, 0x5Cu);
            if ( !v12 )
              goto LABEL_34;
            v13 = v12 + 1;
            if ( (char *)(v12 + 1) - (char *)v7 != 6 || InvStrCmpNIW(v7, L"MY", 2u) )
              goto LABEL_34;
            v14 = v9 - v13;
            if ( v14 == 6 )
            {
              v15 = L"System";
            }
            else
            {
              if ( v14 != 4 )
                goto LABEL_34;
              v15 = L"User";
            }
            if ( InvStrCmpNIW(v13, v15, v14) )
              goto LABEL_34;
            if ( !*v9 )
              break;
            v7 = v9 + 1;
          }
        }
        *a2 = 1;
      }
    }
    else if ( v5 != -2147024882 )
    {
      v4 = 0;
    }
  }
LABEL_34:
  LocalFree(v3);
  SysFreeString(Str);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001bd60  mov     rax, rsp
0x18001bd63  mov     [rax+10h], rbx
0x18001bd67  mov     [rax+20h], rbp
0x18001bd6b  push    rsi
0x18001bd6c  push    rdi
0x18001bd6d  push    r12
0x18001bd6f  push    r14
0x18001bd71  push    r15
0x18001bd73  sub     rsp, 30h
0x18001bd77  xor     r12d, r12d
0x18001bd7a  mov     r14, rdx
0x18001bd7d  mov     [rax+8], r12
0x18001bd81  mov     r15d, r12d
0x18001bd84  mov     [rax+18h], r12
0x18001bd88  test    rcx, rcx
0x18001bd8b  jnz     short loc_18001BD97
0x18001bd8d  mov     ebx, 80004003h
0x18001bd92  jmp     loc_18001BF82
0x18001bd97  test    r14, r14
0x18001bd9a  jz      short loc_18001BD8D
0x18001bd9c  mov     [rdx], r12d
0x18001bd9f  mov     r8, rcx
0x18001bda2  lea     rdx, asc_1800297E8; ".?"
0x18001bda9  mov     ecx, 2
0x18001bdae  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x18001bdb5  nop     dword ptr [rax+rax+00h]
0x18001bdba  mov     r15, rax
0x18001bdbd  test    rax, rax
0x18001bdc0  jnz     short loc_18001BDCC
0x18001bdc2  mov     ebx, 8007000Eh
0x18001bdc7  jmp     loc_18001BF82
0x18001bdcc  xor     edx, edx; pUnkOuter
0x18001bdce  lea     rax, [rsp+58h+arg_0]
0x18001bdd3  lea     r9, _GUID_e34e5896_40b2_45c4_a9c0_8a9601c3b0a6; riid
0x18001bdda  mov     [rsp+58h+ppv], rax; ppv
0x18001bddf  lea     rcx, _GUID_50a41ef1_6bfa_4b7e_973e_798ea0bebad4; rclsid
0x18001bde6  lea     r8d, [rdx+1]; dwClsContext
0x18001bdea  call    cs:__imp_CoCreateInstance
0x18001bdf1  nop     dword ptr [rax+rax+00h]
0x18001bdf6  mov     ebx, eax
0x18001bdf8  test    eax, eax
0x18001bdfa  js      loc_18001BF82
0x18001be00  mov     rcx, [rsp+58h+arg_0]
0x18001be05  mov     rdx, r15
0x18001be08  mov     rax, [rcx]
0x18001be0b  mov     rax, [rax+28h]
0x18001be0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be14  mov     ebx, eax
0x18001be16  test    eax, eax
0x18001be18  jns     short loc_18001BE2D
0x18001be1a  cmp     eax, 8007000Eh
0x18001be1f  jz      loc_18001BF82
0x18001be25  mov     ebx, r12d
0x18001be28  jmp     loc_18001BF82
0x18001be2d  mov     rcx, [rsp+58h+arg_0]
0x18001be32  lea     r8, [rsp+58h+Str]
0x18001be37  lea     rdx, aStores; "Stores"
0x18001be3e  mov     rax, [rcx]
0x18001be41  mov     rax, [rax+80h]
0x18001be48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be4d  cmp     eax, 80070490h
0x18001be52  mov     ebx, r12d
0x18001be55  cmovnz  ebx, eax
0x18001be58  test    ebx, ebx
0x18001be5a  js      loc_18001BF82
0x18001be60  mov     rdi, [rsp+58h+Str]
0x18001be65  test    rdi, rdi
0x18001be68  jz      loc_18001BF7B
0x18001be6e  mov     edx, 0F000h; Ch
0x18001be73  mov     rcx, rdi; Str
0x18001be76  call    cs:__imp_wcschr
0x18001be7d  nop     dword ptr [rax+rax+00h]
0x18001be82  mov     rsi, rax
0x18001be85  test    rax, rax
0x18001be88  jnz     short loc_18001BEDE
0x18001be8a  test    rdi, rdi
0x18001be8d  jz      loc_18001BF74
0x18001be93  mov     edx, 7FFFFFFFh
0x18001be98  mov     rax, rdi
0x18001be9b  cmp     [rax], r12w
0x18001be9f  jz      short loc_18001BEAB
0x18001bea1  add     rax, 2
0x18001bea5  sub     rdx, 1
0x18001bea9  jnz     short loc_18001BE9B
0x18001beab  mov     rax, rdx
0x18001beae  mov     ecx, 7FFFFFFFh
0x18001beb3  neg     rax
0x18001beb6  mov     rax, rdx
0x18001beb9  sbb     ebx, ebx
0x18001bebb  sub     rcx, rdx
0x18001bebe  not     ebx
0x18001bec0  and     ebx, 80070057h
0x18001bec6  neg     rax
0x18001bec9  sbb     r8, r8
0x18001becc  and     r8, rcx
0x18001becf  test    rdx, rdx
0x18001bed2  jz      loc_18001BF82
0x18001bed8  lea     rsi, [rdi+r8*2]
0x18001bedc  jmp     short loc_18001BEE2
0x18001bede  mov     [rax], r12w
0x18001bee2  mov     edx, 5Ch ; '\'; Ch
0x18001bee7  mov     rcx, rdi; Str
0x18001beea  call    cs:__imp_wcschr
0x18001bef1  nop     dword ptr [rax+rax+00h]
0x18001bef6  test    rax, rax
0x18001bef9  jz      loc_18001BF82
0x18001beff  lea     rbp, [rax+2]
0x18001bf03  mov     rax, rbp
0x18001bf06  sub     rax, rdi
0x18001bf09  cmp     rax, 6
0x18001bf0d  jnz     short loc_18001BF82
0x18001bf0f  lea     r8d, [rax-4]
0x18001bf13  mov     rcx, rdi
0x18001bf16  lea     rdx, aMy; "MY"
0x18001bf1d  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x18001bf24  nop     dword ptr [rax+rax+00h]
0x18001bf29  test    eax, eax
0x18001bf2b  jnz     short loc_18001BF82
0x18001bf2d  mov     r8, rsi
0x18001bf30  sub     r8, rbp
0x18001bf33  sar     r8, 1
0x18001bf36  cmp     r8, 6
0x18001bf3a  jnz     short loc_18001BF45
0x18001bf3c  lea     rdx, aSystem; "System"
0x18001bf43  jmp     short loc_18001BF52
0x18001bf45  cmp     r8, 4
0x18001bf49  jnz     short loc_18001BF82
0x18001bf4b  lea     rdx, aUser_1; "User"
0x18001bf52  mov     rcx, rbp
0x18001bf55  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x18001bf5c  nop     dword ptr [rax+rax+00h]
0x18001bf61  test    eax, eax
0x18001bf63  jnz     short loc_18001BF82
0x18001bf65  cmp     r12w, [rsi]
0x18001bf69  jz      short loc_18001BF7B
0x18001bf6b  lea     rdi, [rsi+2]
0x18001bf6f  jmp     loc_18001BE6E
0x18001bf74  mov     ebx, 80070057h
0x18001bf79  jmp     short loc_18001BF82
0x18001bf7b  mov     dword ptr [r14], 1
0x18001bf82  mov     rcx, r15; hMem
0x18001bf85  call    cs:__imp_LocalFree
0x18001bf8c  nop     dword ptr [rax+rax+00h]
0x18001bf91  mov     rcx, [rsp+58h+Str]; bstrString
0x18001bf96  call    cs:__imp_SysFreeString
0x18001bf9d  nop     dword ptr [rax+rax+00h]
0x18001bfa2  mov     rcx, [rsp+58h+arg_0]
0x18001bfa7  test    rcx, rcx
0x18001bfaa  jz      short loc_18001BFB8
0x18001bfac  mov     rax, [rcx]
0x18001bfaf  mov     rax, [rax+10h]
0x18001bfb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bfb8  mov     rbp, [rsp+58h+arg_18]
0x18001bfbd  mov     eax, ebx
0x18001bfbf  mov     rbx, [rsp+58h+arg_8]
0x18001bfc4  add     rsp, 30h
0x18001bfc8  pop     r15
0x18001bfca  pop     r14
0x18001bfcc  pop     r12
0x18001bfce  pop     rdi
0x18001bfcf  pop     rsi
0x18001bfd0  retn
```
