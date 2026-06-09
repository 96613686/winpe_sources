# GetRegistryPolicyDN

- ea: `0x180001220`
- end: `0x1800013c6`
- name: `GetRegistryPolicyDN`
- size: `422`
- prototype: `__int64 __fastcall(LPVOID *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001590`
- `0x180007c5c`

## callees

- `0x180001030`
- `0x180001220`
- `0x180006f60`
- `0x18000e510`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000126f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000126f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800013b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800013b8`

## pseudocode

```c
__int64 __fastcall GetRegistryPolicyDN(LPVOID *a1)
{
  void *v2; // rdi
  unsigned int v3; // eax
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  unsigned int ValueSpd; // eax
  __int64 v10; // [rsp+68h] [rbp+10h] BYREF
  LPVOID lpMem; // [rsp+70h] [rbp+18h]
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  hKey = 0;
  lpMem = 0;
  LODWORD(v10) = 0;
  v2 = 0;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Policies\\Microsoft\\Windows\\IPSEC\\Policy\\Local",
         0,
         0x20019u,
         &hKey);
  v4 = v3;
  if ( !v3 )
  {
    ValueSpd = RegstoreQueryValueSpd(hKey, L"ActivePolicy", (__int64)&v10);
    v4 = ValueSpd;
    if ( !ValueSpd )
    {
      v2 = lpMem;
      if ( lpMem && *(_WORD *)lpMem )
      {
        *a1 = lpMem;
        goto LABEL_25;
      }
      v4 = 14;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_22;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_19;
      v6 = 75;
      v7 = 14;
      goto LABEL_17;
    }
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v2 = lpMem;
LABEL_22:
      if ( v2 )
        IpsecFreeMem(v2);
      goto LABEL_24;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, ValueSpd);
      v2 = lpMem;
LABEL_18:
      v5 = WPP_GLOBAL_Control;
      goto LABEL_19;
    }
    v2 = lpMem;
LABEL_19:
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x10) != 0 )
      WPP_SF_d(v5[2], 76, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, v4);
    goto LABEL_22;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v6 = 73;
      v7 = v3;
LABEL_17:
      WPP_SF_d(v5[2], v6, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, v7);
      goto LABEL_18;
    }
    goto LABEL_19;
  }
LABEL_24:
  *a1 = 0;
LABEL_25:
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x180001220  mov     rax, rsp
0x180001223  mov     [rax+10h], edx
0x180001226  push    rbx
0x180001227  sub     rsp, 50h
0x18000122b  mov     [rax-10h], rbp
0x18000122f  mov     r9d, 20019h; samDesired
0x180001235  mov     [rax-18h], rsi
0x180001239  mov     rsi, rcx
0x18000123c  mov     [rax-20h], rdi
0x180001240  xor     r8d, r8d; ulOptions
0x180001243  mov     [rax-28h], r14
0x180001247  lea     rax, [rax+20h]
0x18000124b  xor     r14d, r14d
0x18000124e  mov     [rsp+58h+phkResult], rax; phkResult
0x180001253  mov     [rax], r14
0x180001256  lea     rdx, SubKey; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18000125d  mov     [rax-8], r14
0x180001261  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180001268  mov     [rax-10h], r14d
0x18000126c  mov     edi, r14d
0x18000126f  call    cs:__imp_RegOpenKeyExW
0x180001275  mov     ebx, eax
0x180001277  test    eax, eax
0x180001279  jz      short loc_1800012A9
0x18000127b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001282  lea     rbp, WPP_GLOBAL_Control
0x180001289  cmp     rcx, rbp
0x18000128c  jz      loc_180001397
0x180001292  test    byte ptr [rcx+1Ch], 10h
0x180001296  jz      loc_180001367
0x18000129c  mov     edx, 49h ; 'I'
0x1800012a1  mov     r9d, eax
0x1800012a4  jmp     loc_180001350
0x1800012a9  mov     rcx, [rsp+58h+hKey]; hKey
0x1800012ae  lea     rax, [rsp+58h+arg_8]
0x1800012b3  lea     r9, [rsp+58h+lpMem]
0x1800012b8  mov     [rsp+58h+phkResult], rax; __int64
0x1800012bd  lea     rdx, aActivepolicy; "ActivePolicy"
0x1800012c4  call    RegstoreQueryValueSpd
0x1800012c9  mov     ebx, eax
0x1800012cb  test    eax, eax
0x1800012cd  jz      short loc_180001315
0x1800012cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800012d6  lea     rbp, WPP_GLOBAL_Control
0x1800012dd  cmp     rcx, rbp
0x1800012e0  jz      short loc_18000130E
0x1800012e2  test    byte ptr [rcx+1Ch], 10h
0x1800012e6  jz      short loc_180001307
0x1800012e8  mov     rcx, [rcx+10h]
0x1800012ec  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x1800012f3  mov     edx, 4Ah ; 'J'
0x1800012f8  mov     r9d, eax
0x1800012fb  call    WPP_SF_d
0x180001300  mov     rdi, [rsp+58h+lpMem]
0x180001305  jmp     short loc_180001360
0x180001307  mov     rdi, [rsp+58h+lpMem]
0x18000130c  jmp     short loc_180001367
0x18000130e  mov     rdi, [rsp+58h+lpMem]
0x180001313  jmp     short loc_18000138A
0x180001315  mov     rdi, [rsp+58h+lpMem]
0x18000131a  test    rdi, rdi
0x18000131d  jz      short loc_18000132A
0x18000131f  cmp     [rdi], r14w
0x180001323  jz      short loc_18000132A
0x180001325  mov     [rsi], rdi
0x180001328  jmp     short loc_18000139A
0x18000132a  mov     ebx, 0Eh
0x18000132f  mov     rcx, cs:WPP_GLOBAL_Control
0x180001336  lea     rbp, WPP_GLOBAL_Control
0x18000133d  cmp     rcx, rbp
0x180001340  jz      short loc_18000138A
0x180001342  test    byte ptr [rcx+1Ch], 10h
0x180001346  jz      short loc_180001367
0x180001348  mov     edx, 4Bh ; 'K'
0x18000134d  mov     r9d, ebx
0x180001350  mov     rcx, [rcx+10h]
0x180001354  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18000135b  call    WPP_SF_d
0x180001360  mov     rcx, cs:WPP_GLOBAL_Control
0x180001367  cmp     rcx, rbp
0x18000136a  jz      short loc_18000138A
0x18000136c  test    byte ptr [rcx+1Ch], 10h
0x180001370  jz      short loc_18000138A
0x180001372  mov     rcx, [rcx+10h]
0x180001376  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18000137d  mov     edx, 4Ch ; 'L'
0x180001382  mov     r9d, ebx
0x180001385  call    WPP_SF_d
0x18000138a  test    rdi, rdi
0x18000138d  jz      short loc_180001397
0x18000138f  mov     rcx, rdi; lpMem
0x180001392  call    IpsecFreeMem
0x180001397  mov     [rsi], r14
0x18000139a  mov     rcx, [rsp+58h+hKey]; hKey
0x18000139f  mov     r14, [rsp+58h+var_28]
0x1800013a4  mov     rdi, [rsp+58h+var_20]
0x1800013a9  mov     rsi, [rsp+58h+var_18]
0x1800013ae  mov     rbp, [rsp+58h+var_10]
0x1800013b3  test    rcx, rcx
0x1800013b6  jz      short loc_1800013BE
0x1800013b8  call    cs:__imp_RegCloseKey
0x1800013be  mov     eax, ebx
0x1800013c0  add     rsp, 50h
0x1800013c4  pop     rbx
0x1800013c5  retn
```
