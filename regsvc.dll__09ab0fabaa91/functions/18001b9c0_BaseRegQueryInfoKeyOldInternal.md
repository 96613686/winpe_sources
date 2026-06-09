# BaseRegQueryInfoKeyOldInternal

- ea: `0x18001b9c0`
- end: `0x18001bd67`
- name: `BaseRegQueryInfoKeyOldInternal`
- size: `935`
- prototype: `__int64 __fastcall(HKEY, __int64, _DWORD *, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001b320`

## callees

- `0x180007740`
- `0x180008042`
- `0x1800084bc`
- `0x18000a7b8`
- `0x18001b9c0`
- `0x18001bd70`
- `0x18001e43d`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001bca1`
- `ntdll!RtlNtStatusToDosError` at `0x18001bca1`
- `ntdll!NtQuerySecurityObject` at `0x18001bb77`
- `ntdll!NtQuerySecurityObject` at `0x18001bba6`
- `ntdll!NtQuerySecurityObject` at `0x18001bb77`
- `ntdll!NtQuerySecurityObject` at `0x18001bba6`
- `ntdll!RtlFreeHeap` at `0x18001bcc4`
- `ntdll!RtlFreeHeap` at `0x18001bcc4`

## pseudocode

```c
__int64 __fastcall BaseRegQueryInfoKeyOldInternal(
        HKEY a1,
        __int64 a2,
        _DWORD *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  __int64 v12; // r12
  __int64 v13; // r13
  __int64 v14; // rdx
  int v15; // r15d
  __int16 *v16; // rsi
  int KeyInfo; // edx
  PULONG v18; // r13
  void *v20; // rcx
  NTSTATUS v21; // ecx
  __int64 p_P; // rbx
  ULONG *v24; // rsi
  ULONG v25; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD *v26; // [rsp+68h] [rbp-98h] BYREF
  PVOID P; // [rsp+70h] [rbp-90h] BYREF
  __int64 v28; // [rsp+78h] [rbp-88h]
  __int64 v29; // [rsp+80h] [rbp-80h]
  __int64 v30; // [rsp+88h] [rbp-78h]
  __int64 v31; // [rsp+90h] [rbp-70h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  PULONG LengthNeeded; // [rsp+A0h] [rbp-60h]
  _DWORD *v34; // [rsp+A8h] [rbp-58h]
  _OWORD SecurityDescriptor[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v36; // [rsp+D0h] [rbp-30h]
  __int64 v37; // [rsp+E0h] [rbp-20h] BYREF
  int v38; // [rsp+ECh] [rbp-14h]
  unsigned int v39; // [rsp+F0h] [rbp-10h]
  int v40; // [rsp+F4h] [rbp-Ch]
  int v41; // [rsp+F8h] [rbp-8h]
  int v42; // [rsp+FCh] [rbp-4h]
  int v43; // [rsp+100h] [rbp+0h]
  int v44; // [rsp+104h] [rbp+4h]
  int v45; // [rsp+108h] [rbp+8h]
  int v46; // [rsp+10Ch] [rbp+Ch] BYREF
  _BYTE v47[176]; // [rsp+190h] [rbp+90h] BYREF

  v31 = a6;
  v30 = a7;
  v29 = a8;
  v28 = a10;
  v26 = a3;
  v36 = 0;
  v25 = 0;
  v32 = a4;
  LengthNeeded = (PULONG)a9;
  v34 = (_DWORD *)a5;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  memset_0(&v37, 0, 0xB0u);
  memset_0(v47, 0, sizeof(v47));
  v12 = a5 & -(__int64)(a5 != 0);
  v13 = a9 & -(__int64)(a9 != 0);
  if ( a1 != HKEY_PERFORMANCE_DATA && a1 != HKEY_PERFORMANCE_TEXT && a1 != HKEY_PERFORMANCE_NLSTEXT )
  {
    v14 = *(_QWORD *)(a2 + 8);
    if ( v14 || v12 )
    {
      v16 = (__int16 *)(a2 + 2);
      v15 = 2;
    }
    else
    {
      v15 = 4;
      v16 = (__int16 *)(a2 + 2);
    }
    P = &v37;
    KeyInfo = QueryKeyInfo(a1, v14 != 0, *v16);
    if ( (int)(KeyInfo + 0x80000000) < 0 || KeyInfo == -2147483643 )
    {
      if ( v15 == 2 )
        *(_WORD *)a2 = *((_WORD *)P + 8) + 2;
      if ( KeyInfo >= 0 )
      {
        if ( v13 )
        {
          v18 = LengthNeeded;
          if ( NtQuerySecurityObject(a1, 7u, SecurityDescriptor, 0, LengthNeeded) == -1073741789 )
          {
            if ( NtQuerySecurityObject(a1, 0xFu, SecurityDescriptor, 0, &v25) == -1073741789 )
              *v18 = v25;
          }
          else
          {
            *LengthNeeded = 0;
          }
        }
        if ( v15 == 4 )
        {
          *v26 = v38;
          *(_DWORD *)v32 = v39;
          *(_DWORD *)v31 = v40;
          *(_DWORD *)v30 = v41;
          *(_DWORD *)v29 = v42;
          *(_QWORD *)v28 = v37;
          return 0;
        }
        *v26 = v40;
        if ( v12 )
          *v34 = v42;
        *(_DWORD *)v32 = v41;
        *(_DWORD *)v31 = v43;
        *(_DWORD *)v30 = v44;
        *(_DWORD *)v29 = v45;
        *(_QWORD *)v28 = v37;
        v20 = *(void **)(a2 + 8);
        if ( !v20 )
          return 0;
        if ( *(_WORD *)a2 <= (unsigned __int16)*v16 )
        {
          if ( v39 )
            memmove_0(v20, &v46, v39);
          *(_WORD *)(*(_QWORD *)(a2 + 8) + 2 * ((unsigned __int64)v39 >> 1)) = 0;
          return 0;
        }
        *(_WORD *)a2 = *v16;
        v21 = -1073741789;
        *(_QWORD *)(a2 + 8) = 0;
        return RtlNtStatusToDosError(v21);
      }
      if ( KeyInfo == -2147483643 )
      {
        *(_QWORD *)(a2 + 8) = 0;
        return 234;
      }
    }
    v21 = KeyInfo;
    return RtlNtStatusToDosError(v21);
  }
  LODWORD(v26) = 0;
  p_P = (__int64)&P;
  if ( v12 )
    p_P = a5 & -(__int64)(a5 != 0);
  v24 = (ULONG *)&v26;
  if ( v13 )
    v24 = (ULONG *)(a9 & -(__int64)(a9 != 0));
  if ( (unsigned __int8)IsPerfRegQueryValuePresent() )
    return PerfRegQueryInfoKey(a1, v32, p_P, v31, v30, v29, v24, v28);
  else
    return 87;
}

```

## disassembly

```asm
0x18001b9c0  push    rbp
0x18001b9c2  push    rbx
0x18001b9c3  push    rsi
0x18001b9c4  push    rdi
0x18001b9c5  push    r12
0x18001b9c7  push    r13
0x18001b9c9  push    r14
0x18001b9cb  push    r15
0x18001b9cd  lea     rbp, [rsp-158h]
0x18001b9d5  sub     rsp, 258h
0x18001b9dc  mov     rax, cs:__security_cookie
0x18001b9e3  xor     rax, rsp
0x18001b9e6  mov     [rbp+190h+var_50], rax
0x18001b9ed  mov     rax, [rbp+190h+arg_28]
0x18001b9f4  xorps   xmm0, xmm0
0x18001b9f7  mov     rsi, [rbp+190h+arg_40]
0x18001b9fe  mov     r15, r8
0x18001ba01  mov     r13, [rbp+190h+arg_20]
0x18001ba08  mov     rdi, rdx
0x18001ba0b  mov     [rbp+190h+var_200], rax
0x18001ba0f  mov     r14, rcx
0x18001ba12  mov     rax, [rbp+190h+arg_30]
0x18001ba19  lea     rcx, [rbp+190h+var_1B0]; void *
0x18001ba1d  mov     [rbp+190h+var_208], rax
0x18001ba21  mov     ebx, 0B0h
0x18001ba26  mov     rax, [rbp+190h+arg_38]
0x18001ba2d  xor     edx, edx; Val
0x18001ba2f  mov     [rbp+190h+var_210], rax
0x18001ba33  mov     rax, [rbp+190h+arg_48]
0x18001ba3a  mov     [rsp+290h+var_218], rax
0x18001ba3f  xor     eax, eax
0x18001ba41  mov     [rsp+290h+var_228], r8
0x18001ba46  mov     r8d, ebx; Size
0x18001ba49  mov     [rbp+190h+var_1C0], rax
0x18001ba4d  mov     [rsp+290h+var_230], eax
0x18001ba51  mov     [rbp+190h+var_1F8], r9
0x18001ba55  mov     [rbp+190h+var_1F0], rsi
0x18001ba59  mov     [rbp+190h+var_1E8], r13
0x18001ba5d  movups  [rbp+190h+SecurityDescriptor], xmm0
0x18001ba61  movups  [rbp+190h+var_1D0], xmm0
0x18001ba65  call    memset_0
0x18001ba6a  mov     r8d, ebx; Size
0x18001ba6d  lea     rcx, [rbp+190h+var_100]; void *
0x18001ba74  xor     edx, edx; Val
0x18001ba76  call    memset_0
0x18001ba7b  mov     rax, r13
0x18001ba7e  neg     rax
0x18001ba81  mov     rax, rsi
0x18001ba84  sbb     r12, r12
0x18001ba87  and     r12, r13
0x18001ba8a  neg     rax
0x18001ba8d  sbb     r13, r13
0x18001ba90  and     r13, rsi
0x18001ba93  cmp     r14, 0FFFFFFFF80000004h
0x18001ba9a  jz      loc_18001BCCE
0x18001baa0  cmp     r14, 0FFFFFFFF80000050h
0x18001baa7  jz      loc_18001BCCE
0x18001baad  cmp     r14, 0FFFFFFFF80000060h
0x18001bab4  jz      loc_18001BCCE
0x18001baba  mov     rdx, [rdi+8]
0x18001babe  test    rdx, rdx
0x18001bac1  jnz     short loc_18001BAD5
0x18001bac3  test    r12, r12
0x18001bac6  jnz     short loc_18001BAD5
0x18001bac8  lea     ebx, [rdx+28h]
0x18001bacb  lea     r15d, [rdx+4]
0x18001bacf  lea     rsi, [rdi+2]
0x18001bad3  jmp     short loc_18001BAED
0x18001bad5  lea     rsi, [rdi+2]
0x18001bad9  mov     r15d, 2
0x18001badf  movzx   ecx, word ptr [rsi]
0x18001bae2  cmp     ecx, 83h
0x18001bae8  ja      short loc_18001BAED
0x18001baea  lea     ebx, [rcx+2Ch]
0x18001baed  xor     ecx, ecx
0x18001baef  lea     rax, [rbp+190h+var_1B0]
0x18001baf3  test    rdx, rdx
0x18001baf6  mov     [rsp+290h+P], rax
0x18001bafb  movzx   eax, word ptr [rsi]
0x18001bafe  lea     r8, [rsp+290h+P]
0x18001bb03  setnz   cl
0x18001bb06  mov     [rsp+290h+var_268], ax; __int16
0x18001bb0b  mov     dword ptr [rsp+290h+LengthNeeded], ecx; int
0x18001bb0f  mov     r9d, ebx
0x18001bb12  mov     rcx, r14; KeyHandle
0x18001bb15  mov     edx, r15d
0x18001bb18  call    QueryKeyInfo
0x18001bb1d  mov     rbx, [rsp+290h+P]
0x18001bb22  mov     edx, eax
0x18001bb24  mov     eax, 80000000h
0x18001bb29  mov     r8d, 80000005h
0x18001bb2f  lea     ecx, [rdx+rax]
0x18001bb32  test    eax, ecx
0x18001bb34  jnz     short loc_18001BB3F
0x18001bb36  cmp     edx, r8d
0x18001bb39  jnz     loc_18001BC9F
0x18001bb3f  mov     ecx, 2
0x18001bb44  cmp     r15d, ecx
0x18001bb47  jnz     short loc_18001BB53
0x18001bb49  movzx   eax, word ptr [rbx+10h]
0x18001bb4d  add     ax, cx
0x18001bb50  mov     [rdi], ax
0x18001bb53  test    edx, edx
0x18001bb55  js      loc_18001BC8B
0x18001bb5b  test    r13, r13
0x18001bb5e  jz      short loc_18001BBBB
0x18001bb60  mov     r13, [rbp+190h+var_1F0]
0x18001bb64  lea     r8, [rbp+190h+SecurityDescriptor]; SecurityDescriptor
0x18001bb68  xor     r9d, r9d; Length
0x18001bb6b  mov     [rsp+290h+LengthNeeded], r13; LengthNeeded
0x18001bb70  mov     rcx, r14; Handle
0x18001bb73  lea     edx, [r9+7]; SecurityInformation
0x18001bb77  call    cs:__imp_NtQuerySecurityObject
0x18001bb7d  cmp     eax, 0C0000023h
0x18001bb82  jz      short loc_18001BB8E
0x18001bb84  mov     dword ptr [r13+0], 0
0x18001bb8c  jmp     short loc_18001BBBB
0x18001bb8e  xor     r9d, r9d; Length
0x18001bb91  lea     rax, [rsp+290h+var_230]
0x18001bb96  lea     r8, [rbp+190h+SecurityDescriptor]; SecurityDescriptor
0x18001bb9a  mov     [rsp+290h+LengthNeeded], rax; LengthNeeded
0x18001bb9f  mov     rcx, r14; Handle
0x18001bba2  lea     edx, [r9+0Fh]; SecurityInformation
0x18001bba6  call    cs:__imp_NtQuerySecurityObject
0x18001bbac  cmp     eax, 0C0000023h
0x18001bbb1  jnz     short loc_18001BBBB
0x18001bbb3  mov     eax, [rsp+290h+var_230]
0x18001bbb7  mov     [r13+0], eax
0x18001bbbb  mov     rcx, [rsp+290h+var_228]
0x18001bbc0  cmp     r15d, 4
0x18001bbc4  jnz     short loc_18001BC01
0x18001bbc6  mov     eax, [rbx+0Ch]
0x18001bbc9  mov     [rcx], eax
0x18001bbcb  mov     eax, [rbx+10h]
0x18001bbce  mov     rcx, [rbp+190h+var_1F8]
0x18001bbd2  mov     [rcx], eax
0x18001bbd4  mov     eax, [rbx+14h]
0x18001bbd7  mov     rcx, [rbp+190h+var_200]
0x18001bbdb  mov     [rcx], eax
0x18001bbdd  mov     eax, [rbx+18h]
0x18001bbe0  mov     rcx, [rbp+190h+var_208]
0x18001bbe4  mov     [rcx], eax
0x18001bbe6  mov     eax, [rbx+1Ch]
0x18001bbe9  mov     rcx, [rbp+190h+var_210]
0x18001bbed  mov     [rcx], eax
0x18001bbef  mov     rcx, [rsp+290h+var_218]
0x18001bbf4  mov     rax, [rbx]
0x18001bbf7  mov     [rcx], rax
0x18001bbfa  xor     edi, edi
0x18001bbfc  jmp     loc_18001BCA9
0x18001bc01  mov     eax, [rbx+14h]
0x18001bc04  mov     [rcx], eax
0x18001bc06  test    r12, r12
0x18001bc09  jz      short loc_18001BC14
0x18001bc0b  mov     rcx, [rbp+190h+var_1E8]
0x18001bc0f  mov     eax, [rbx+1Ch]
0x18001bc12  mov     [rcx], eax
0x18001bc14  mov     eax, [rbx+18h]
0x18001bc17  mov     rcx, [rbp+190h+var_1F8]
0x18001bc1b  mov     [rcx], eax
0x18001bc1d  mov     eax, [rbx+20h]
0x18001bc20  mov     rcx, [rbp+190h+var_200]
0x18001bc24  mov     [rcx], eax
0x18001bc26  mov     eax, [rbx+24h]
0x18001bc29  mov     rcx, [rbp+190h+var_208]
0x18001bc2d  mov     [rcx], eax
0x18001bc2f  mov     eax, [rbx+28h]
0x18001bc32  mov     rcx, [rbp+190h+var_210]
0x18001bc36  mov     [rcx], eax
0x18001bc38  mov     rcx, [rsp+290h+var_218]
0x18001bc3d  mov     rax, [rbx]
0x18001bc40  mov     [rcx], rax
0x18001bc43  mov     rcx, [rdi+8]; void *
0x18001bc47  test    rcx, rcx
0x18001bc4a  jz      short loc_18001BBFA
0x18001bc4c  movzx   eax, word ptr [rsi]
0x18001bc4f  cmp     [rdi], ax
0x18001bc52  ja      short loc_18001BC79
0x18001bc54  cmp     dword ptr [rbx+10h], 0
0x18001bc58  jz      short loc_18001BC67
0x18001bc5a  mov     r8d, [rbx+10h]; Size
0x18001bc5e  lea     rdx, [rbx+2Ch]; Src
0x18001bc62  call    memmove_0
0x18001bc67  mov     edx, [rbx+10h]
0x18001bc6a  mov     rcx, [rdi+8]
0x18001bc6e  shr     rdx, 1
0x18001bc71  xor     eax, eax
0x18001bc73  mov     [rcx+rdx*2], ax
0x18001bc77  jmp     short loc_18001BBFA
0x18001bc79  mov     [rdi], ax
0x18001bc7c  mov     ecx, 0C0000023h
0x18001bc81  mov     qword ptr [rdi+8], 0
0x18001bc89  jmp     short loc_18001BCA1
0x18001bc8b  cmp     edx, r8d
0x18001bc8e  jnz     short loc_18001BC9F
0x18001bc90  mov     qword ptr [rdi+8], 0
0x18001bc98  mov     edi, 0EAh
0x18001bc9d  jmp     short loc_18001BCA9
0x18001bc9f  mov     ecx, edx; Status
0x18001bca1  call    cs:__imp_RtlNtStatusToDosError
0x18001bca7  mov     edi, eax
0x18001bca9  lea     rax, [rbp+190h+var_1B0]
0x18001bcad  cmp     rbx, rax
0x18001bcb0  jz      short loc_18001BCCA
0x18001bcb2  mov     rcx, gs:60h
0x18001bcbb  mov     r8, rbx; P
0x18001bcbe  xor     edx, edx; Flags
0x18001bcc0  mov     rcx, [rcx+30h]; HeapHandle
0x18001bcc4  call    cs:__imp_RtlFreeHeap
0x18001bcca  mov     eax, edi
0x18001bccc  jmp     short loc_18001BD44
0x18001bcce  test    r12, r12
0x18001bcd1  mov     dword ptr [rsp+290h+var_228], 0
0x18001bcd9  lea     rbx, [rsp+290h+P]
0x18001bcde  cmovnz  rbx, r12
0x18001bce2  lea     rsi, [rsp+290h+var_228]
0x18001bce7  test    r13, r13
0x18001bcea  cmovnz  rsi, r13
0x18001bcee  call    IsPerfRegQueryValuePresent
0x18001bcf3  test    al, al
0x18001bcf5  jz      short loc_18001BD3F
0x18001bcf7  mov     rcx, [rsp+290h+var_218]
0x18001bcfc  mov     r9, r15
0x18001bcff  mov     [rsp+290h+var_240], rcx; __int64
0x18001bd04  mov     rdx, rdi
0x18001bd07  mov     rcx, [rbp+190h+var_210]
0x18001bd0b  mov     [rsp+290h+var_248], rsi; PULONG
0x18001bd10  mov     [rsp+290h+var_250], rcx; __int64
0x18001bd15  mov     rcx, [rbp+190h+var_208]
0x18001bd19  mov     [rsp+290h+var_258], rcx; __int64
0x18001bd1e  mov     rcx, [rbp+190h+var_200]
0x18001bd22  mov     [rsp+290h+var_260], rcx; __int64
0x18001bd27  mov     rcx, [rbp+190h+var_1F8]
0x18001bd2b  mov     qword ptr [rsp+290h+var_268], rbx; __int64
0x18001bd30  mov     [rsp+290h+LengthNeeded], rcx; __int64
0x18001bd35  mov     rcx, r14; HKEY
0x18001bd38  call    PerfRegQueryInfoKey
0x18001bd3d  jmp     short loc_18001BD44
0x18001bd3f  mov     eax, 57h ; 'W'
0x18001bd44  mov     rcx, [rbp+190h+var_50]
0x18001bd4b  xor     rcx, rsp; StackCookie
0x18001bd4e  call    __security_check_cookie
0x18001bd53  add     rsp, 258h
0x18001bd5a  pop     r15
0x18001bd5c  pop     r14
0x18001bd5e  pop     r13
0x18001bd60  pop     r12
0x18001bd62  pop     rdi
0x18001bd63  pop     rsi
0x18001bd64  pop     rbx
0x18001bd65  pop     rbp
0x18001bd66  retn
```
