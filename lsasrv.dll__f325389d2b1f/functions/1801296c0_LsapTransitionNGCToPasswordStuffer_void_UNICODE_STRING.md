# LsapTransitionNGCToPasswordStuffer(void *,_UNICODE_STRING *)

- ea: `0x1801296c0`
- end: `0x180129ade`
- name: `?LsapTransitionNGCToPasswordStuffer@@YAXPEAXPEAU_UNICODE_STRING@@@Z`
- size: `1054`
- prototype: `void __fastcall(PSID Sid, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180125c28`

## callees

- `0x180009330`
- `0x180011278`
- `0x180060cb0`
- `0x18008e360`
- `0x1800ada18`
- `0x1800b86d0`
- `0x1800bb284`
- `0x1800bd6e0`
- `0x180123860`
- `0x1801296c0`
- `0x18014a6b0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180129a42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180129a5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180129a42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180129a5b`
- `ntdll!RtlGetLastNtStatus` at `0x18012973f`
- `ntdll!RtlGetLastNtStatus` at `0x18012973f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18012970e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18012970e`
- `ext-ms-win-security-ngc-local-l1-1-0!NgcLocalAddCredential` at `0x1801299ab`
- `ext-ms-win-security-ngc-local-l1-1-0!NgcLocalAddCredential` at `0x1801299ab`
- `cryptngc!NgcDeleteContainerEx` at `0x180129848`
- `cryptngc!NgcDeleteContainerEx` at `0x1801299fa`
- `cryptngc!NgcDeleteContainerEx` at `0x180129848`
- `cryptngc!NgcDeleteContainerEx` at `0x1801299fa`
- `cryptngc!NgcEnumContainers` at `0x18012977a`
- `cryptngc!NgcEnumContainers` at `0x18012977a`
- `cryptngc!NgcFreeEnumState` at `0x180129a74`
- `cryptngc!NgcFreeEnumState` at `0x180129a74`

## pseudocode

```c
void __fastcall LsapTransitionNGCToPasswordStuffer(PSID Sid, struct _UNICODE_STRING *a2)
{
  void *p_StringSid; // rdi
  unsigned __int64 v4; // r14
  NTSTATUS LastNtStatus; // eax
  LsaHandleCache *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  int v10; // eax
  LsaHandleCache *v11; // rcx
  int v12; // edx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  LsaHandleCache *v16; // rcx
  __int64 v17; // rdx
  unsigned __int64 v18; // rcx
  __int64 v19; // rcx
  void *v20; // rsp
  void *v21; // rsp
  _DWORD *v22; // rax
  int v23; // eax
  __int64 v24; // rcx
  _BYTE *v25; // rax
  __int64 v26; // [rsp+0h] [rbp-30h] BYREF
  LPWSTR StringSid; // [rsp+30h] [rbp+0h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp+8h] BYREF
  __int64 v29; // [rsp+40h] [rbp+10h] BYREF

  hMem = 0;
  v29 = 0;
  p_StringSid = 0;
  StringSid = 0;
  LODWORD(v4) = 0;
  CONNECTED_TRACE_ENTER("LsapTransitionNGCToPasswordStuffer");
  if ( !ConvertSidToStringSidW(Sid, &StringSid) )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      LastNtStatus = RtlGetLastNtStatus();
      v7 = WPP_GLOBAL_Control;
      v8 = 54;
LABEL_5:
      v9 = (unsigned int)LastNtStatus;
LABEL_6:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_da3d202165313132ccfab67d2692d0fe_Traceguids, v9);
      goto LABEL_54;
    }
    goto LABEL_54;
  }
  LastNtStatus = NgcEnumContainers(StringSid, &hMem, &v29);
  if ( LastNtStatus == -2146893782 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v8 = 55;
      v9 = 2148073514LL;
      goto LABEL_6;
    }
    goto LABEL_54;
  }
  if ( LastNtStatus >= 0 )
  {
    if ( !hMem || *((_QWORD *)hMem + 4) || *((_QWORD *)hMem + 5) )
      goto LABEL_54;
    if ( !a2->Length )
    {
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_da3d202165313132ccfab67d2692d0fe_Traceguids);
      v10 = NgcDeleteContainerEx(StringSid, 1);
      if ( v10 >= 0 )
        goto LABEL_54;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_54;
      v12 = 58;
      goto LABEL_53;
    }
    if ( (unsigned __int8)IsNgcLocalRemoveCredentialPresent() )
    {
      v4 = (unsigned int)a2->Length + 2;
      if ( v4 > g_ulMaxStackAllocSize )
        goto LABEL_68;
      v18 = v4 + g_ulAdditionalProbeSize + 8;
      if ( v18 < v4 || !(unsigned int)VerifyStackAvailable(v18, v13, v14, v15) )
        goto LABEL_68;
      v19 = v4 + 23;
      if ( v4 + 23 <= v4 + 8 )
        v19 = 0xFFFFFFFFFFFFFF0LL;
      v20 = alloca(v19 & 0xFFFFFFFFFFFFFFF0uLL);
      v21 = alloca(v19 & 0xFFFFFFFFFFFFFFF0uLL);
      p_StringSid = &StringSid;
      if ( &v26 == (__int64 *)-48LL || (LODWORD(StringSid) = 1801679955, (p_StringSid = &hMem) == 0) )
      {
LABEL_68:
        if ( v4 + 8 >= v4 )
        {
          v22 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
          p_StringSid = v22;
          if ( v22 )
          {
            *v22 = 1885431112;
            p_StringSid = v22 + 2;
          }
        }
      }
      if ( p_StringSid )
      {
        memcpy_0(p_StringSid, a2->Buffer, a2->Length);
        *((_WORD *)p_StringSid + (v4 >> 1) - 1) = 0;
        v23 = NgcLocalAddCredential(StringSid, p_StringSid, 0);
        if ( v23 >= 0 )
          goto LABEL_54;
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            61,
            (unsigned int)WPP_da3d202165313132ccfab67d2692d0fe_Traceguids,
            (_DWORD)StringSid,
            v23);
        }
        v10 = NgcDeleteContainerEx(StringSid, 1);
        if ( v10 >= 0 )
          goto LABEL_54;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        {
          goto LABEL_54;
        }
        v12 = 62;
LABEL_53:
        WPP_SF_Sd(
          *((_QWORD *)v11 + 2),
          v12,
          (unsigned int)WPP_da3d202165313132ccfab67d2692d0fe_Traceguids,
          (_DWORD)StringSid,
          v10);
        goto LABEL_54;
      }
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      {
        goto LABEL_54;
      }
      v17 = 60;
    }
    else
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_54;
      v17 = 59;
    }
    WPP_SF_(*((_QWORD *)v16 + 2), v17, WPP_da3d202165313132ccfab67d2692d0fe_Traceguids);
    goto LABEL_54;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v8 = 56;
    goto LABEL_5;
  }
LABEL_54:
  if ( StringSid )
  {
    LocalFree(StringSid);
    StringSid = 0;
  }
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( v29 )
  {
    NgcFreeEnumState();
    v29 = 0;
  }
  if ( p_StringSid )
  {
    v24 = (unsigned int)v4;
    v25 = p_StringSid;
    if ( (_DWORD)v4 )
    {
      do
      {
        *v25++ = 0;
        --v24;
      }
      while ( v24 );
    }
    if ( *((_DWORD *)p_StringSid - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
  CONNECTED_TRACE_EXIT_VOID("LsapTransitionNGCToPasswordStuffer");
}

```

## disassembly

```asm
0x1801296c0  push    rbp
0x1801296c2  push    rbx
0x1801296c3  push    rsi
0x1801296c4  push    rdi
0x1801296c5  push    r14
0x1801296c7  push    r15
0x1801296c9  sub     rsp, 68h
0x1801296cd  lea     rbp, [rsp+30h]
0x1801296d2  mov     rax, cs:__security_cookie
0x1801296d9  xor     rax, rbp
0x1801296dc  mov     [rbp+60h+var_40], rax
0x1801296e0  xor     r15d, r15d
0x1801296e3  mov     rbx, rcx
0x1801296e6  lea     rcx, aLsaptransition; "LsapTransitionNGCToPasswordStuffer"
0x1801296ed  mov     [rbp+60h+hMem], r15
0x1801296f1  mov     [rbp+60h+var_50], r15
0x1801296f5  mov     edi, r15d
0x1801296f8  mov     [rbp+60h+StringSid], r15
0x1801296fc  mov     r14d, r15d
0x1801296ff  mov     rsi, rdx
0x180129702  call    CONNECTED_TRACE_ENTER
0x180129707  lea     rdx, [rbp+60h+StringSid]; StringSid
0x18012970b  mov     rcx, rbx; Sid
0x18012970e  call    cs:__imp_ConvertSidToStringSidW
0x180129715  nop     dword ptr [rax+rax+00h]
0x18012971a  test    eax, eax
0x18012971c  jnz     short loc_18012976E
0x18012971e  mov     rax, cs:WPP_GLOBAL_Control
0x180129725  lea     rbx, WPP_GLOBAL_Control
0x18012972c  cmp     rax, rbx
0x18012972f  jz      loc_180129A39
0x180129735  test    byte ptr [rax+1Ch], 2
0x180129739  jz      loc_180129A39
0x18012973f  call    cs:__imp_RtlGetLastNtStatus
0x180129746  nop     dword ptr [rax+rax+00h]
0x18012974b  mov     rcx, cs:WPP_GLOBAL_Control
0x180129752  lea     edx, [r15+36h]
0x180129756  mov     r9d, eax
0x180129759  mov     rcx, [rcx+10h]
0x18012975d  lea     r8, WPP_da3d202165313132ccfab67d2692d0fe_Traceguids
0x180129764  call    WPP_SF_d
0x180129769  jmp     loc_180129A39
0x18012976e  mov     rcx, [rbp+60h+StringSid]
0x180129772  lea     r8, [rbp+60h+var_50]
0x180129776  lea     rdx, [rbp+60h+hMem]
0x18012977a  call    cs:__imp_NgcEnumContainers
0x180129781  nop     dword ptr [rax+rax+00h]
0x180129786  cmp     eax, 8009002Ah
0x18012978b  jnz     short loc_1801297BB
0x18012978d  mov     rcx, cs:WPP_GLOBAL_Control
0x180129794  lea     rbx, WPP_GLOBAL_Control
0x18012979b  cmp     rcx, rbx
0x18012979e  jz      loc_180129A39
0x1801297a4  test    byte ptr [rcx+1Ch], 4
0x1801297a8  jz      loc_180129A39
0x1801297ae  mov     edx, 37h ; '7'
0x1801297b3  mov     r9d, 8009002Ah
0x1801297b9  jmp     short loc_180129759
0x1801297bb  test    eax, eax
0x1801297bd  jns     short loc_1801297EA
0x1801297bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1801297c6  lea     rbx, WPP_GLOBAL_Control
0x1801297cd  cmp     rcx, rbx
0x1801297d0  jz      loc_180129A39
0x1801297d6  test    byte ptr [rcx+1Ch], 2
0x1801297da  jz      loc_180129A39
0x1801297e0  mov     edx, 38h ; '8'
0x1801297e5  jmp     loc_180129756
0x1801297ea  mov     rcx, [rbp+60h+hMem]
0x1801297ee  test    rcx, rcx
0x1801297f1  jz      loc_180129A39
0x1801297f7  cmp     [rcx+20h], r15
0x1801297fb  jnz     loc_180129A39
0x180129801  cmp     [rcx+28h], r15
0x180129805  jnz     loc_180129A39
0x18012980b  cmp     [rsi], r15w
0x18012980f  jnz     short loc_180129880
0x180129811  mov     rcx, cs:WPP_GLOBAL_Control
0x180129818  lea     rbx, WPP_GLOBAL_Control
0x18012981f  cmp     rcx, rbx
0x180129822  jz      short loc_18012983F
0x180129824  test    byte ptr [rcx+1Ch], 4
0x180129828  jz      short loc_18012983F
0x18012982a  mov     rcx, [rcx+10h]
0x18012982e  lea     r8, WPP_da3d202165313132ccfab67d2692d0fe_Traceguids
0x180129835  mov     edx, 39h ; '9'
0x18012983a  call    WPP_SF_
0x18012983f  mov     rcx, [rbp+60h+StringSid]
0x180129843  mov     edx, 1
0x180129848  call    cs:__imp_NgcDeleteContainerEx
0x18012984f  nop     dword ptr [rax+rax+00h]
0x180129854  test    eax, eax
0x180129856  jns     loc_180129A39
0x18012985c  mov     rcx, cs:WPP_GLOBAL_Control
0x180129863  cmp     rcx, rbx
0x180129866  jz      loc_180129A39
0x18012986c  test    byte ptr [rcx+1Ch], 2
0x180129870  jz      loc_180129A39
0x180129876  mov     edx, 3Ah ; ':'
0x18012987b  jmp     loc_180129A21
0x180129880  call    IsNgcLocalRemoveCredentialPresent
0x180129885  test    al, al
0x180129887  jnz     short loc_1801298C4
0x180129889  mov     rcx, cs:WPP_GLOBAL_Control
0x180129890  lea     rbx, WPP_GLOBAL_Control
0x180129897  cmp     rcx, rbx
0x18012989a  jz      loc_180129A39
0x1801298a0  test    byte ptr [rcx+1Ch], 2
0x1801298a4  jz      loc_180129A39
0x1801298aa  mov     edx, 3Bh ; ';'
0x1801298af  mov     rcx, [rcx+10h]
0x1801298b3  lea     r8, WPP_da3d202165313132ccfab67d2692d0fe_Traceguids
0x1801298ba  call    WPP_SF_
0x1801298bf  jmp     loc_180129A39
0x1801298c4  movzx   r14d, word ptr [rsi]
0x1801298c8  add     r14d, 2
0x1801298cc  mov     ebx, r14d
0x1801298cf  cmp     rbx, cs:g_ulMaxStackAllocSize
0x1801298d6  ja      short loc_180129930
0x1801298d8  mov     rcx, cs:g_ulAdditionalProbeSize
0x1801298df  add     rcx, 8
0x1801298e3  add     rcx, rbx
0x1801298e6  cmp     rcx, rbx
0x1801298e9  jb      short loc_180129930
0x1801298eb  call    VerifyStackAvailable
0x1801298f0  test    eax, eax
0x1801298f2  jz      short loc_180129930
0x1801298f4  lea     rax, [r14+8]
0x1801298f8  lea     rcx, [rax+0Fh]
0x1801298fc  cmp     rcx, rax
0x1801298ff  ja      short loc_18012990B
0x180129901  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18012990b  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18012990f  mov     rax, rcx
0x180129912  call    _alloca_probe
0x180129917  sub     rsp, rcx
0x18012991a  lea     rdi, [rsp+90h+StringSid]
0x18012991f  test    rdi, rdi
0x180129922  jz      short loc_180129930
0x180129924  mov     dword ptr [rdi], 6B637453h
0x18012992a  add     rdi, 8
0x18012992e  jnz     short loc_180129957
0x180129930  lea     rcx, [r14+8]
0x180129934  cmp     rcx, rbx
0x180129937  jb      short loc_180129957
0x180129939  mov     rax, cs:g_pfnAllocate
0x180129940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129945  mov     rdi, rax
0x180129948  test    rax, rax
0x18012994b  jz      short loc_180129957
0x18012994d  mov     dword ptr [rax], 70616548h
0x180129953  add     rdi, 8
0x180129957  test    rdi, rdi
0x18012995a  jnz     short loc_180129988
0x18012995c  mov     rcx, cs:WPP_GLOBAL_Control
0x180129963  lea     rbx, WPP_GLOBAL_Control
0x18012996a  cmp     rcx, rbx
0x18012996d  jz      loc_180129A39
0x180129973  test    dword ptr [rcx+1Ch], 200h
0x18012997a  jz      loc_180129A39
0x180129980  lea     edx, [rdi+3Ch]
0x180129983  jmp     loc_1801298AF
0x180129988  movzx   r8d, word ptr [rsi]; Size
0x18012998c  mov     rcx, rdi; void *
0x18012998f  mov     rdx, [rsi+8]; Src
0x180129993  call    memcpy_0
0x180129998  shr     rbx, 1
0x18012999b  xor     r8d, r8d
0x18012999e  mov     rdx, rdi
0x1801299a1  mov     [rdi+rbx*2-2], r15w
0x1801299a7  mov     rcx, [rbp+60h+StringSid]
0x1801299ab  call    cs:__imp_NgcLocalAddCredential
0x1801299b2  nop     dword ptr [rax+rax+00h]
0x1801299b7  test    eax, eax
0x1801299b9  jns     short loc_180129A39
0x1801299bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1801299c2  lea     rbx, WPP_GLOBAL_Control
0x1801299c9  cmp     rcx, rbx
0x1801299cc  jz      short loc_1801299F1
0x1801299ce  test    byte ptr [rcx+1Ch], 2
0x1801299d2  jz      short loc_1801299F1
0x1801299d4  mov     r9, [rbp+60h+StringSid]
0x1801299d8  lea     r8, WPP_da3d202165313132ccfab67d2692d0fe_Traceguids
0x1801299df  mov     rcx, [rcx+10h]
0x1801299e3  mov     edx, 3Dh ; '='
0x1801299e8  mov     [rsp+90h+var_70], eax
0x1801299ec  call    WPP_SF_Sd
0x1801299f1  mov     rcx, [rbp+60h+StringSid]
0x1801299f5  mov     edx, 1
0x1801299fa  call    cs:__imp_NgcDeleteContainerEx
0x180129a01  nop     dword ptr [rax+rax+00h]
0x180129a06  test    eax, eax
0x180129a08  jns     short loc_180129A39
0x180129a0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180129a11  cmp     rcx, rbx
0x180129a14  jz      short loc_180129A39
0x180129a16  test    byte ptr [rcx+1Ch], 2
0x180129a1a  jz      short loc_180129A39
0x180129a1c  mov     edx, 3Eh ; '>'
0x180129a21  mov     r9, [rbp+60h+StringSid]
0x180129a25  lea     r8, WPP_da3d202165313132ccfab67d2692d0fe_Traceguids
0x180129a2c  mov     rcx, [rcx+10h]
0x180129a30  mov     [rsp+90h+var_70], eax
0x180129a34  call    WPP_SF_Sd
0x180129a39  mov     rcx, [rbp+60h+StringSid]; hMem
0x180129a3d  test    rcx, rcx
0x180129a40  jz      short loc_180129A52
0x180129a42  call    cs:__imp_LocalFree
0x180129a49  nop     dword ptr [rax+rax+00h]
0x180129a4e  mov     [rbp+60h+StringSid], r15
0x180129a52  mov     rcx, [rbp+60h+hMem]; hMem
0x180129a56  test    rcx, rcx
0x180129a59  jz      short loc_180129A6B
0x180129a5b  call    cs:__imp_LocalFree
0x180129a62  nop     dword ptr [rax+rax+00h]
0x180129a67  mov     [rbp+60h+hMem], r15
0x180129a6b  mov     rcx, [rbp+60h+var_50]
0x180129a6f  test    rcx, rcx
0x180129a72  jz      short loc_180129A84
0x180129a74  call    cs:__imp_NgcFreeEnumState
0x180129a7b  nop     dword ptr [rax+rax+00h]
0x180129a80  mov     [rbp+60h+var_50], r15
0x180129a84  test    rdi, rdi
0x180129a87  jz      short loc_180129AB8
0x180129a89  mov     ecx, r14d
0x180129a8c  mov     rax, rdi
0x180129a8f  test    r14d, r14d
0x180129a92  jz      short loc_180129AA0
0x180129a94  mov     [rax], r15b
0x180129a97  inc     rax
0x180129a9a  sub     rcx, 1
0x180129a9e  jnz     short loc_180129A94
0x180129aa0  lea     rcx, [rdi-8]
0x180129aa4  cmp     dword ptr [rcx], 70616548h
0x180129aaa  jnz     short loc_180129AB8
0x180129aac  mov     rax, cs:g_pfnFree
0x180129ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129ab8  lea     rcx, aLsaptransition; "LsapTransitionNGCToPasswordStuffer"
0x180129abf  call    CONNECTED_TRACE_EXIT_VOID
0x180129ac4  mov     rcx, [rbp+60h+var_40]
0x180129ac8  xor     rcx, rbp; StackCookie
0x180129acb  call    __security_check_cookie
0x180129ad0  lea     rsp, [rbp+38h]
0x180129ad4  pop     r15
0x180129ad6  pop     r14
0x180129ad8  pop     rdi
0x180129ad9  pop     rsi
0x180129ada  pop     rbx
0x180129adb  pop     rbp
0x180129adc  retn
```
