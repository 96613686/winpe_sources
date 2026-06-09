# DiscpReportIScsiSendTargetPortalsEx

- ea: `0x180005118`
- end: `0x180005286`
- name: `DiscpReportIScsiSendTargetPortalsEx`
- size: `366`
- prototype: `__int64 __fastcall(_DWORD *, unsigned int *, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004310`

## callees

- `0x180005118`

## import_xrefs

- `ISCSIUM!DiscpEnumerateRegistryValues` at `0x1800051b7`
- `ISCSIUM!DiscpEnumerateRegistryValues` at `0x180005237`
- `ISCSIUM!DiscpEnumerateRegistryValues` at `0x1800051b7`
- `ISCSIUM!DiscpEnumerateRegistryValues` at `0x180005237`

## pseudocode

```c
__int64 __fastcall DiscpReportIScsiSendTargetPortalsEx(_DWORD *a1, unsigned int *a2, __int64 a3, __int64 a4, char a5)
{
  __int64 v5; // r14
  int v10; // ebx
  unsigned int v11; // ecx
  unsigned int v12; // eax
  unsigned int v13; // edx
  int v14; // eax
  int v15; // ebx
  int v17; // [rsp+20h] [rbp-51h]
  char v18; // [rsp+40h] [rbp-31h] BYREF
  char v19; // [rsp+41h] [rbp-30h]
  __int16 v20; // [rsp+42h] [rbp-2Fh]
  _BYTE v21[12]; // [rsp+44h] [rbp-2Dh] BYREF
  __int128 v22; // [rsp+50h] [rbp-21h]
  __int64 v23; // [rsp+60h] [rbp-11h]
  __int64 v24; // [rsp+68h] [rbp-9h]
  __int64 v25; // [rsp+70h] [rbp-1h]

  v20 = 0;
  v5 = a4;
  v25 = 0;
  if ( !a5 )
    v5 = a3;
  v18 = a5;
  v23 = 0;
  v24 = 0;
  v19 = 1;
  memset(v21, 0, sizeof(v21));
  v10 = a5 != 0 ? 848 : 1616;
  v22 = 0;
  DiscpEnumerateRegistryValues(
    0,
    L"Software\\Microsoft\\Windows NT\\CurrentVersion\\iSCSI\\Discovery\\Send Targets",
    3,
    1608,
    1,
    &DiscpTargetPortalCallback,
    &v18);
  v11 = v25;
  if ( !(_DWORD)v25 )
  {
    if ( !*(_DWORD *)v21 )
    {
      *a1 = 0;
      *a2 = 0;
      return v11;
    }
    v12 = *a2;
    v13 = *(_DWORD *)v21 * v10 + *(_DWORD *)&v21[4];
    if ( v13 > *a2 )
    {
      *a1 = *(_DWORD *)v21;
      v11 = 122;
      *a2 = v13;
      return v11;
    }
    LODWORD(v24) = *(_DWORD *)v21 * v10;
    HIDWORD(v24) = v12 - *(_DWORD *)v21 * v10;
    v23 = v5;
    *(_QWORD *)&v22 = a3;
    LOBYTE(v17) = 1;
    *((_QWORD *)&v22 + 1) = a4;
    *(_DWORD *)&v21[8] = *(_DWORD *)v21;
    v19 = 0;
    *(_QWORD *)v21 = 0;
    LODWORD(v25) = 0;
    DiscpEnumerateRegistryValues(
      0,
      L"Software\\Microsoft\\Windows NT\\CurrentVersion\\iSCSI\\Discovery\\Send Targets",
      3,
      1608,
      v17,
      &DiscpTargetPortalCallback,
      &v18);
    v11 = v25;
    if ( (_DWORD)v25 )
    {
      if ( (_DWORD)v25 != 122 )
        return v11;
      v15 = *(_DWORD *)v21 * v10;
    }
    else
    {
      v14 = *(_DWORD *)v21;
      *a1 = *(_DWORD *)v21;
      v15 = v14 * v10;
    }
    *a2 = *(_DWORD *)&v21[4] + v15;
  }
  return v11;
}

```

## disassembly

```asm
0x180005118  push    rbp
0x18000511a  push    rbx
0x18000511b  push    rsi
0x18000511c  push    rdi
0x18000511d  push    r12
0x18000511f  push    r13
0x180005121  push    r14
0x180005123  push    r15
0x180005125  lea     rbp, [rsp-17h]
0x18000512a  sub     rsp, 88h
0x180005131  mov     r10b, [rbp+4Fh+arg_20]
0x180005135  xor     r13d, r13d
0x180005138  test    r10b, r10b
0x18000513b  mov     [rbp+4Fh+var_7E], r13w
0x180005140  mov     r14, r9
0x180005143  mov     [rbp+4Fh+var_50], r13
0x180005147  cmovz   r14, r8
0x18000514b  mov     [rbp+4Fh+var_80], r10b
0x18000514f  mov     al, r10b
0x180005152  mov     [rbp+4Fh+var_60], r13
0x180005156  neg     al
0x180005158  mov     [rbp+4Fh+var_58], r13
0x18000515c  lea     rax, [rbp+4Fh+var_80]
0x180005160  mov     qword ptr [rbp+4Fh+var_7C+4], r13
0x180005164  mov     [rsp+0C0h+var_90], rax
0x180005169  sbb     ebx, ebx
0x18000516b  lea     rax, DiscpTargetPortalCallback
0x180005172  mov     [rbp+4Fh+var_7F], 1
0x180005176  mov     r15, r9
0x180005179  mov     [rsp+0C0h+var_98], rax
0x18000517e  mov     r12, r8
0x180005181  mov     [rsp+0C0h+var_A0], 1
0x180005186  mov     rdi, rdx
0x180005189  mov     dword ptr [rbp+4Fh+var_7C], r13d
0x18000518d  mov     rsi, rcx
0x180005190  lea     r8d, [r13+3]
0x180005194  xorps   xmm0, xmm0
0x180005197  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x18000519e  and     ebx, 0FFFFFD00h
0x1800051a4  mov     r9d, 648h
0x1800051aa  xor     ecx, ecx
0x1800051ac  add     ebx, 650h
0x1800051b2  movdqu  [rbp+4Fh+var_70], xmm0
0x1800051b7  call    cs:__imp_DiscpEnumerateRegistryValues
0x1800051bd  mov     ecx, dword ptr [rbp+4Fh+var_50]
0x1800051c0  test    ecx, ecx
0x1800051c2  jnz     loc_180005270
0x1800051c8  mov     r10d, dword ptr [rbp+4Fh+var_7C]
0x1800051cc  test    r10d, r10d
0x1800051cf  jz      loc_18000526A
0x1800051d5  mov     edx, dword ptr [rbp+4Fh+var_7C+4]
0x1800051d8  mov     ecx, ebx
0x1800051da  mov     eax, [rdi]
0x1800051dc  imul    ecx, r10d
0x1800051e0  add     edx, ecx
0x1800051e2  cmp     edx, eax
0x1800051e4  ja      short loc_18000525E
0x1800051e6  sub     eax, ecx
0x1800051e8  mov     dword ptr [rbp+4Fh+var_58], ecx
0x1800051eb  mov     dword ptr [rbp+4Fh+var_58+4], eax
0x1800051ee  lea     r8d, [r13+3]
0x1800051f2  lea     rax, [rbp+4Fh+var_80]
0x1800051f6  mov     [rbp+4Fh+var_60], r14
0x1800051fa  mov     [rsp+0C0h+var_90], rax
0x1800051ff  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x180005206  lea     rax, DiscpTargetPortalCallback
0x18000520d  mov     qword ptr [rbp+4Fh+var_70], r12
0x180005211  mov     [rsp+0C0h+var_98], rax
0x180005216  mov     r9d, 648h
0x18000521c  xor     ecx, ecx
0x18000521e  mov     [rsp+0C0h+var_A0], 1
0x180005223  mov     qword ptr [rbp+4Fh+var_70+8], r15
0x180005227  mov     dword ptr [rbp+4Fh+var_7C+8], r10d
0x18000522b  mov     [rbp+4Fh+var_7F], r13b
0x18000522f  mov     qword ptr [rbp+4Fh+var_7C], r13
0x180005233  mov     dword ptr [rbp+4Fh+var_50], r13d
0x180005237  call    cs:__imp_DiscpEnumerateRegistryValues
0x18000523d  mov     ecx, dword ptr [rbp+4Fh+var_50]
0x180005240  test    ecx, ecx
0x180005242  jnz     short loc_180005253
0x180005244  mov     eax, dword ptr [rbp+4Fh+var_7C]
0x180005247  mov     [rsi], eax
0x180005249  imul    ebx, eax
0x18000524c  add     ebx, dword ptr [rbp+4Fh+var_7C+4]
0x18000524f  mov     [rdi], ebx
0x180005251  jmp     short loc_180005270
0x180005253  cmp     ecx, 7Ah ; 'z'
0x180005256  jnz     short loc_180005270
0x180005258  imul    ebx, dword ptr [rbp+4Fh+var_7C]
0x18000525c  jmp     short loc_18000524C
0x18000525e  mov     [rsi], r10d
0x180005261  mov     ecx, 7Ah ; 'z'
0x180005266  mov     [rdi], edx
0x180005268  jmp     short loc_180005270
0x18000526a  mov     [rsi], r13d
0x18000526d  mov     [rdi], r13d
0x180005270  mov     eax, ecx
0x180005272  add     rsp, 88h
0x180005279  pop     r15
0x18000527b  pop     r14
0x18000527d  pop     r13
0x18000527f  pop     r12
0x180005281  pop     rdi
0x180005282  pop     rsi
0x180005283  pop     rbx
0x180005284  pop     rbp
0x180005285  retn
```
