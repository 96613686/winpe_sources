# CiLogSIPolicySmartlockerEvent

- ea: `0x1800a11e8`
- end: `0x1800a14dd`
- name: `CiLogSIPolicySmartlockerEvent`
- size: `757`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800e24c0`

## callees

- `0x18002bef0`
- `0x1800a0250`
- `0x1800a11e8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1800a1494`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a14a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a1494`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a14a7`
- `ntoskrnl!EtwEventEnabled` at `0x1800a1339`
- `ntoskrnl!EtwEventEnabled` at `0x1800a1339`
- `ntoskrnl!IoGetActivityIdThread` at `0x1800a144c`
- `ntoskrnl!IoGetActivityIdThread` at `0x1800a144c`
- `ntoskrnl!EtwWrite` at `0x1800a1475`
- `ntoskrnl!EtwWrite` at `0x1800a1475`

## pseudocode

```c
__int64 __fastcall CiLogSIPolicySmartlockerEvent(const wchar_t *a1, unsigned int a2, unsigned int a3, int a4, int a5)
{
  __int64 v6; // rcx
  NTSTATUS PolicyNameAndID; // esi
  PVOID *v8; // r15
  PVOID *v9; // r13
  bool v10; // r14
  bool v11; // zf
  __int64 *v12; // rax
  __int64 *v13; // rbx
  int v14; // ecx
  __int64 v15; // rcx
  unsigned __int16 v16; // ax
  const GUID *ActivityIdThread; // rax
  __int16 v19; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v20; // [rsp+34h] [rbp-CCh] BYREF
  __int16 v21; // [rsp+38h] [rbp-C8h] BYREF
  int v22; // [rsp+3Ch] [rbp-C4h] BYREF
  int v23; // [rsp+40h] [rbp-C0h] BYREF
  int v24; // [rsp+44h] [rbp-BCh] BYREF
  int v25; // [rsp+48h] [rbp-B8h] BYREF
  int v26; // [rsp+4Ch] [rbp-B4h] BYREF
  PVOID P[2]; // [rsp+50h] [rbp-B0h] BYREF
  PVOID v28[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-90h] BYREF
  __int64 v30; // [rsp+80h] [rbp-80h]
  int v31; // [rsp+88h] [rbp-78h]
  int v32; // [rsp+8Ch] [rbp-74h]
  int *v33; // [rsp+90h] [rbp-70h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  int *v35; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  int *v37; // [rsp+B0h] [rbp-50h]
  __int64 v38; // [rsp+B8h] [rbp-48h]
  int *v39; // [rsp+C0h] [rbp-40h]
  __int64 v40; // [rsp+C8h] [rbp-38h]
  int *v41; // [rsp+D0h] [rbp-30h]
  __int64 v42; // [rsp+D8h] [rbp-28h]
  int *v43; // [rsp+E0h] [rbp-20h]
  __int64 v44; // [rsp+E8h] [rbp-18h]
  int *v45; // [rsp+F0h] [rbp-10h]
  __int64 v46; // [rsp+F8h] [rbp-8h]
  __int16 *v47; // [rsp+100h] [rbp+0h]
  __int64 v48; // [rsp+108h] [rbp+8h]
  PVOID v49; // [rsp+110h] [rbp+10h]
  int v50; // [rsp+118h] [rbp+18h]
  int v51; // [rsp+11Ch] [rbp+1Ch]
  __int16 *v52; // [rsp+120h] [rbp+20h]
  __int64 v53; // [rsp+128h] [rbp+28h]
  PVOID v54; // [rsp+130h] [rbp+30h]
  int v55; // [rsp+138h] [rbp+38h]
  int v56; // [rsp+13Ch] [rbp+3Ch]
  int v57; // [rsp+1A8h] [rbp+A8h] BYREF

  v57 = a4;
  v22 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v6 = *((_QWORD *)g_SiPolicyHandles + a2);
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  *(_OWORD *)P = 0;
  *(_OWORD *)v28 = 0;
  v22 = *(_WORD *)(v6 + 46) & 1;
  if ( !a1 || *a1 <= 2u )
    a1 = L"\b\n";
  v23 = (*(_DWORD *)(v6 + 44) >> 27) & 1;
  v25 = (*(_DWORD *)(v6 + 44) >> 4) & 1;
  v24 = a3 & 1;
  v26 = (a3 >> 1) & 1;
  PolicyNameAndID = CiLogSIPolicyGetPolicyNameAndID(v6, P, v28);
  v8 = v28;
  v9 = P;
  if ( PolicyNameAndID < 0 )
  {
    v8 = (PVOID *)L"TV";
    v9 = (PVOID *)L"TV";
  }
  v10 = PolicyNameAndID >= 0;
  v19 = *a1 >> 1;
  if ( a5 < 0 )
  {
    v11 = v22 == 0;
    v13 = SmartlockerOperationalAudit;
    v12 = SmartlockerOperationalFailure;
  }
  else
  {
    v11 = (g_CiTestFlags & 0x200) == 0;
    v12 = (__int64 *)&SmartlockerVerbose;
    v13 = SmartlockerOperationalSuccess;
  }
  if ( v11 )
    v13 = v12;
  if ( EtwEventEnabled(g_EtwEventHandle, (PCEVENT_DESCRIPTOR)v13) )
  {
    v14 = *(unsigned __int16 *)v9;
    UserData.Ptr = (ULONGLONG)&v19;
    v30 = *((_QWORD *)a1 + 1);
    v31 = *a1;
    v33 = &a5;
    v35 = &v23;
    v37 = &v24;
    v39 = &v25;
    v41 = &v26;
    v43 = &v57;
    v45 = &v22;
    v20 = (unsigned __int16)v14 >> 1;
    v47 = &v20;
    v49 = v9[1];
    v50 = v14;
    v15 = *(unsigned __int16 *)v8;
    v16 = *(_WORD *)v8;
    *(_QWORD *)&UserData.Size = 2;
    v21 = v16 >> 1;
    v52 = &v21;
    v54 = v8[1];
    v32 = 0;
    v34 = 4;
    v36 = 4;
    v38 = 4;
    v40 = 4;
    v42 = 4;
    v44 = 4;
    v46 = 4;
    v48 = 2;
    v51 = 0;
    v53 = 2;
    v55 = v15;
    v56 = 0;
    ActivityIdThread = (const GUID *)IoGetActivityIdThread(v15);
    PolicyNameAndID = EtwWrite(g_EtwEventHandle, (PCEVENT_DESCRIPTOR)v13, ActivityIdThread, 0xDu, &UserData);
  }
  if ( v10 )
  {
    ExFreePoolWithTag(P[1], 0x63734943u);
    ExFreePoolWithTag(v28[1], 0x63734943u);
  }
  return (unsigned int)PolicyNameAndID;
}

```

## disassembly

```asm
0x1800a11e8  mov     [rsp-8+arg_0], rbx
0x1800a11ed  mov     [rsp-8+arg_18], r9d
0x1800a11f2  push    rbp
0x1800a11f3  push    rsi
0x1800a11f4  push    rdi
0x1800a11f5  push    r12
0x1800a11f7  push    r13
0x1800a11f9  push    r14
0x1800a11fb  push    r15
0x1800a11fd  lea     rbp, [rsp-50h]
0x1800a1202  sub     rsp, 150h
0x1800a1209  mov     rax, cs:__security_cookie
0x1800a1210  xor     rax, rsp
0x1800a1213  mov     [rbp+80h+var_40], rax
0x1800a1217  mov     rax, cs:g_SiPolicyHandles
0x1800a121e  xor     r12d, r12d
0x1800a1221  mov     rdi, rcx
0x1800a1224  mov     [rsp+180h+var_144], r12d
0x1800a1229  mov     ecx, edx
0x1800a122b  xorps   xmm0, xmm0
0x1800a122e  xorps   xmm1, xmm1
0x1800a1231  mov     [rsp+180h+var_150], r12w
0x1800a1237  lea     ebx, [r12+1]
0x1800a123c  mov     [rsp+180h+var_14C], r12w
0x1800a1242  mov     [rsp+180h+var_148], r12w
0x1800a1248  mov     rcx, [rax+rcx*8]
0x1800a124c  mov     [rsp+180h+var_140], r12d
0x1800a1251  mov     [rsp+180h+var_13C], r12d
0x1800a1256  mov     [rsp+180h+var_138], r12d
0x1800a125b  mov     [rsp+180h+var_134], r12d
0x1800a1260  movups  xmmword ptr [rsp+180h+P], xmm0
0x1800a1265  movups  xmmword ptr [rsp+180h+var_120], xmm1
0x1800a126a  movzx   eax, word ptr [rcx+2Eh]
0x1800a126e  and     eax, ebx
0x1800a1270  mov     [rsp+180h+var_144], eax
0x1800a1274  lea     eax, [rbx+1]
0x1800a1277  test    rdi, rdi
0x1800a127a  jz      short loc_1800A1281
0x1800a127c  cmp     [rdi], ax
0x1800a127f  ja      short loc_1800A1288
0x1800a1281  lea     rdi, asc_18002EF88; "\b\n"
0x1800a1288  mov     eax, [rcx+2Ch]
0x1800a128b  lea     rdx, [rsp+180h+P]
0x1800a1290  shr     eax, 1Bh
0x1800a1293  and     eax, ebx
0x1800a1295  mov     [rsp+180h+var_140], eax
0x1800a1299  mov     eax, [rcx+2Ch]
0x1800a129c  shr     eax, 4
0x1800a129f  and     eax, ebx
0x1800a12a1  mov     [rsp+180h+var_138], eax
0x1800a12a5  mov     eax, r8d
0x1800a12a8  shr     r8d, 1
0x1800a12ab  and     eax, ebx
0x1800a12ad  and     r8d, ebx
0x1800a12b0  mov     [rsp+180h+var_13C], eax
0x1800a12b4  mov     [rsp+180h+var_134], r8d
0x1800a12b9  lea     r8, [rsp+180h+var_120]
0x1800a12be  call    CiLogSIPolicyGetPolicyNameAndID
0x1800a12c3  mov     esi, eax
0x1800a12c5  lea     r15, [rsp+180h+var_120]
0x1800a12ca  test    esi, esi
0x1800a12cc  lea     rax, aTv; "TV"
0x1800a12d3  lea     r13, [rsp+180h+P]
0x1800a12d8  mov     r14d, esi
0x1800a12db  cmovs   r15, rax
0x1800a12df  cmovs   r13, rax
0x1800a12e3  movzx   eax, word ptr [rdi]
0x1800a12e6  shr     r14d, 1Fh
0x1800a12ea  shr     ax, 1
0x1800a12ed  xor     r14b, bl
0x1800a12f0  mov     [rsp+180h+var_150], ax
0x1800a12f5  cmp     [rbp+80h+arg_20], r12d
0x1800a12fc  jl      short loc_1800A1318
0x1800a12fe  test    cs:g_CiTestFlags, 200h
0x1800a1308  lea     rax, SmartlockerVerbose
0x1800a130f  lea     rbx, SmartlockerOperationalSuccess
0x1800a1316  jmp     short loc_1800A132B
0x1800a1318  cmp     [rsp+180h+var_144], r12d
0x1800a131d  lea     rbx, SmartlockerOperationalAudit
0x1800a1324  lea     rax, SmartlockerOperationalFailure
0x1800a132b  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x1800a1332  cmovz   rbx, rax
0x1800a1336  mov     rdx, rbx; EventDescriptor
0x1800a1339  call    cs:__imp_EtwEventEnabled
0x1800a1340  nop     dword ptr [rax+rax+00h]
0x1800a1345  test    al, al
0x1800a1347  jz      loc_1800A1483
0x1800a134d  movzx   ecx, word ptr [r13+0]
0x1800a1352  lea     rax, [rsp+180h+var_150]
0x1800a1357  mov     [rsp+180h+var_110.Ptr], rax
0x1800a135c  mov     rax, [rdi+8]
0x1800a1360  mov     [rbp+80h+var_100], rax
0x1800a1364  movzx   eax, word ptr [rdi]
0x1800a1367  mov     [rbp+80h+var_F8], eax
0x1800a136a  lea     rax, [rbp+80h+arg_20]
0x1800a1371  mov     [rbp+80h+var_F0], rax
0x1800a1375  lea     rax, [rsp+180h+var_140]
0x1800a137a  mov     [rbp+80h+var_E0], rax
0x1800a137e  lea     rax, [rsp+180h+var_13C]
0x1800a1383  mov     [rbp+80h+var_D0], rax
0x1800a1387  lea     rax, [rsp+180h+var_138]
0x1800a138c  mov     [rbp+80h+var_C0], rax
0x1800a1390  lea     rax, [rsp+180h+var_134]
0x1800a1395  mov     [rbp+80h+var_B0], rax
0x1800a1399  lea     rax, [rbp+80h+arg_18]
0x1800a13a0  mov     [rbp+80h+var_A0], rax
0x1800a13a4  lea     rax, [rsp+180h+var_144]
0x1800a13a9  mov     [rbp+80h+var_90], rax
0x1800a13ad  movzx   eax, cx
0x1800a13b0  shr     ax, 1
0x1800a13b3  mov     [rsp+180h+var_14C], ax
0x1800a13b8  lea     rax, [rsp+180h+var_14C]
0x1800a13bd  mov     [rbp+80h+var_80], rax
0x1800a13c1  mov     rax, [r13+8]
0x1800a13c5  mov     [rbp+80h+var_70], rax
0x1800a13c9  mov     [rbp+80h+var_68], ecx
0x1800a13cc  movzx   ecx, word ptr [r15]
0x1800a13d0  movzx   eax, cx
0x1800a13d3  mov     qword ptr [rsp+180h+var_110.Size], 2
0x1800a13dc  shr     ax, 1
0x1800a13df  mov     [rsp+180h+var_148], ax
0x1800a13e4  lea     rax, [rsp+180h+var_148]
0x1800a13e9  mov     [rbp+80h+var_60], rax
0x1800a13ed  mov     rax, [r15+8]
0x1800a13f1  mov     [rbp+80h+var_50], rax
0x1800a13f5  mov     [rbp+80h+var_F4], r12d
0x1800a13f9  mov     [rbp+80h+var_E8], 4
0x1800a1401  mov     [rbp+80h+var_D8], 4
0x1800a1409  mov     [rbp+80h+var_C8], 4
0x1800a1411  mov     [rbp+80h+var_B8], 4
0x1800a1419  mov     [rbp+80h+var_A8], 4
0x1800a1421  mov     [rbp+80h+var_98], 4
0x1800a1429  mov     [rbp+80h+var_88], 4
0x1800a1431  mov     [rbp+80h+var_78], 2
0x1800a1439  mov     [rbp+80h+var_64], r12d
0x1800a143d  mov     [rbp+80h+var_58], 2
0x1800a1445  mov     [rbp+80h+var_48], ecx
0x1800a1448  mov     [rbp+80h+var_44], r12d
0x1800a144c  call    cs:__imp_IoGetActivityIdThread
0x1800a1453  nop     dword ptr [rax+rax+00h]
0x1800a1458  lea     rcx, [rsp+180h+var_110]
0x1800a145d  mov     r9d, 0Dh; UserDataCount
0x1800a1463  mov     [rsp+180h+UserData], rcx; UserData
0x1800a1468  mov     r8, rax; ActivityId
0x1800a146b  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x1800a1472  mov     rdx, rbx; EventDescriptor
0x1800a1475  call    cs:__imp_EtwWrite
0x1800a147c  nop     dword ptr [rax+rax+00h]
0x1800a1481  mov     esi, eax
0x1800a1483  test    r14b, r14b
0x1800a1486  jz      short loc_1800A14B3
0x1800a1488  mov     rcx, [rsp+180h+P+8]; P
0x1800a148d  mov     ebx, 63734943h
0x1800a1492  mov     edx, ebx; Tag
0x1800a1494  call    cs:__imp_ExFreePoolWithTag
0x1800a149b  nop     dword ptr [rax+rax+00h]
0x1800a14a0  mov     rcx, [rsp+180h+var_120+8]; P
0x1800a14a5  mov     edx, ebx; Tag
0x1800a14a7  call    cs:__imp_ExFreePoolWithTag
0x1800a14ae  nop     dword ptr [rax+rax+00h]
0x1800a14b3  mov     eax, esi
0x1800a14b5  mov     rcx, [rbp+80h+var_40]
0x1800a14b9  xor     rcx, rsp; StackCookie
0x1800a14bc  call    __security_check_cookie
0x1800a14c1  mov     rbx, [rsp+180h+arg_0]
0x1800a14c9  add     rsp, 150h
0x1800a14d0  pop     r15
0x1800a14d2  pop     r14
0x1800a14d4  pop     r13
0x1800a14d6  pop     r12
0x1800a14d8  pop     rdi
0x1800a14d9  pop     rsi
0x1800a14da  pop     rbp
0x1800a14db  retn
```
