# CreateAppContainerFromPolicyWorker(ushort const *,_APPCONTAINER_PREDEFINED_POLICIES,void * *)

- ea: `0x18001dbe0`
- end: `0x18001dc9d`
- name: `?CreateAppContainerFromPolicyWorker@@YAJPEBGW4_APPCONTAINER_PREDEFINED_POLICIES@@PEAPEAX@Z`
- size: `189`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004594`
- `0x18001dbe0`
- `0x18001dcb0`

## string_xrefs

- `0x18001dbf8`: `onecore\ds\security\gina\profile\profext\lpacapi.cpp`
- `0x18001dc32`: `onecore\ds\security\gina\profile\profext\lpacpolicystore.cpp`

## pseudocode

```c
__int64 __fastcall CreateAppContainerFromPolicyWorker(char *a1, int a2, void **a3)
{
  __int64 v3; // rdx
  int AppContainerWorker; // ebx
  int v6[2]; // [rsp+20h] [rbp-28h] BYREF
  const struct _APPCONTAINER_CAPABILITY near *const *v7; // [rsp+28h] [rbp-20h]
  const struct _APPCONTAINER_MITIGATIONS near *const *v8; // [rsp+30h] [rbp-18h]
  int v9; // [rsp+38h] [rbp-10h]
  int v10; // [rsp+3Ch] [rbp-Ch]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !a1 )
  {
    v3 = 84;
LABEL_3:
    AppContainerWorker = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacapi.cpp",
      (const char *)(unsigned int)AppContainerWorker,
      v6[0]);
    return (unsigned int)AppContainerWorker;
  }
  if ( !a3 )
  {
    v3 = 85;
    goto LABEL_3;
  }
  v6[1] = 0;
  v10 = 0;
  if ( a2 )
  {
    AppContainerWorker = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacpolicystore.cpp",
      (const char *)0x80070057LL,
      v6[0]);
    v3 = 89;
    goto LABEL_4;
  }
  v7 = &LpacPolicyStore::m_PolicyDefaultCapabilities;
  v8 = &LpacPolicyStore::m_PolicyDefaultMitigations;
  v6[0] = 10;
  v9 = 0;
  AppContainerWorker = CreateAppContainerWorker(a1, (struct _APPCONTAINER_POLICY *)v6, a3);
  if ( AppContainerWorker < 0 )
  {
    v3 = 90;
    goto LABEL_4;
  }
  return 0;
}

```

## disassembly

```asm
0x18001dbe0  push    rbx
0x18001dbe2  sub     rsp, 40h
0x18001dbe6  test    rcx, rcx
0x18001dbe9  jnz     short loc_18001DC0E
0x18001dbeb  lea     edx, [rcx+54h]; void *
0x18001dbee  mov     ebx, 80070057h
0x18001dbf3  mov     rcx, [rsp+48h]; this
0x18001dbf8  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001dbff  mov     r9d, ebx; char *
0x18001dc02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dc07  mov     eax, ebx
0x18001dc09  jmp     loc_18001DC96
0x18001dc0e  test    r8, r8
0x18001dc11  jnz     short loc_18001DC19
0x18001dc13  lea     edx, [r8+55h]
0x18001dc17  jmp     short loc_18001DBEE
0x18001dc19  mov     [rsp+48h+var_24], 0
0x18001dc21  mov     [rsp+48h+var_C], 0
0x18001dc29  test    edx, edx
0x18001dc2b  jz      short loc_18001DC52
0x18001dc2d  mov     rcx, [rsp+48h]; this
0x18001dc32  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001dc39  mov     ebx, 80070057h
0x18001dc3e  mov     edx, 1Ah; void *
0x18001dc43  mov     r9d, ebx; char *
0x18001dc46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dc4b  mov     edx, 59h ; 'Y'
0x18001dc50  jmp     short loc_18001DBF3
0x18001dc52  mov     rax, cs:off_180025E88
0x18001dc59  lea     rdx, [rsp+48h+var_28]; struct _APPCONTAINER_POLICY *
0x18001dc5e  mov     [rsp+48h+var_20], rax
0x18001dc63  mov     rax, cs:off_180025E90
0x18001dc6a  mov     [rsp+48h+var_18], rax
0x18001dc6f  mov     [rsp+48h+var_28], 0Ah
0x18001dc77  mov     [rsp+48h+var_10], 0
0x18001dc7f  call    ?CreateAppContainerWorker@@YAJPEBGPEAU_APPCONTAINER_POLICY@@PEAPEAX@Z; CreateAppContainerWorker(ushort const *,_APPCONTAINER_POLICY *,void * *)
0x18001dc84  mov     ebx, eax
0x18001dc86  test    eax, eax
0x18001dc88  jns     short loc_18001DC94
0x18001dc8a  mov     edx, 5Ah ; 'Z'
0x18001dc8f  jmp     loc_18001DBF3
0x18001dc94  xor     eax, eax
0x18001dc96  add     rsp, 40h
0x18001dc9a  pop     rbx
0x18001dc9b  retn
```
