# DbgKdTransport::WriteDataPacket(void *,ushort,ushort,void *,ushort,int,ulong *)

- ea: `0x1801d11e0`
- end: `0x1801d1571`
- name: `?WriteDataPacket@DbgKdTransport@@QEAAJPEAXGG0GHPEAK@Z`
- size: `913`
- prototype: `__int64 __fastcall(DbgKdTransport *__hidden this, void *, unsigned __int16, unsigned __int16, void *, unsigned __int16, int, unsigned int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1801d1580`
- `0x1801d1790`

## callees

- `0x1800793cc`
- `0x180098580`
- `0x1800b94c4`
- `0x1800c12b8`
- `0x1800e8b30`
- `0x1800f0f40`
- `0x1801ce6a0`
- `0x1801d11e0`
- `0x1801d15b4`
- `0x1801d195c`
- `0x18038605c`
- `0x1804387fc`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1801d12e2`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1801d12e2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801d1542`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801d1542`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801d126f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801d126f`
- `api-ms-win-core-misc-l1-1-0!Sleep` at `0x1801d146f`
- `api-ms-win-core-misc-l1-1-0!Sleep` at `0x1801d146f`

## string_xrefs

- `0x1801d127f`: `Kernel transport in use, packet write failed\n`
- `0x1801d129e`: `WRITE: Write type %s packet\n`
- `0x1801d152e`: `WriteDataPacket interrupted by exit request\n`
- `0x1801d14f9`: `to an address that is not valid for the local computer. %s\n`
- `0x1801d1500`: `Cannot write on the current requested socket/address.This normally results from an attempt to bind `

## pseudocode

```c
__int64 __fastcall DbgKdTransport::WriteDataPacket(
        DbgKdTransport *this,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        unsigned __int8 *a5,
        unsigned __int16 a6,
        int a7,
        unsigned int *a8)
{
  unsigned __int8 *v8; // r13
  unsigned __int16 v9; // r15
  __int64 v11; // rax
  __int64 v13; // r14
  __int64 v14; // rcx
  unsigned int v15; // esi
  int v16; // ebx
  unsigned __int8 *v17; // rbx
  __int64 v18; // rax
  unsigned __int64 v19; // rcx
  unsigned __int16 v20; // r11
  unsigned __int8 *v21; // rax
  int *v22; // r8
  unsigned __int8 *v23; // rdx
  int v24; // eax
  bool v25; // zf
  unsigned int v26; // r12d
  unsigned int v27; // eax
  unsigned __int16 v28; // r11
  char v29; // dl
  int v30; // r10d
  unsigned __int16 v31; // r9
  char v32; // r14
  int v33; // eax
  int v34; // eax
  unsigned __int16 *v35; // rax
  unsigned __int16 *v36; // rax
  int v38; // [rsp+38h] [rbp-79h]
  unsigned __int16 v39; // [rsp+44h] [rbp-6Dh]
  int v40; // [rsp+48h] [rbp-69h]
  unsigned __int8 *v41; // [rsp+50h] [rbp-61h]
  int v42; // [rsp+58h] [rbp-59h] BYREF
  __int16 v43; // [rsp+5Ch] [rbp-55h]
  unsigned __int16 v44; // [rsp+5Eh] [rbp-53h]
  __int64 v45; // [rsp+60h] [rbp-51h]
  _OWORD v46[3]; // [rsp+68h] [rbp-49h] BYREF
  int v47; // [rsp+98h] [rbp-19h]

  v8 = a5;
  v9 = a6;
  v47 = 0;
  v11 = *((_QWORD *)this + 8);
  memset(v46, 0, sizeof(v46));
  v13 = (unsigned __int16)a4;
  v39 = a3;
  v14 = *(unsigned int *)(v11 + 4224);
  v41 = a2;
  v45 = 0;
  if ( (_DWORD)v14 )
  {
    if ( (unsigned __int16)a4 >= (unsigned int)v14 )
LABEL_5:
      MicrosoftTelemetryAssertTriggeredNoArgs(v14, a2, a3, a4);
  }
  else if ( (unsigned __int16)a4 >= 0xCu )
  {
    goto LABEL_5;
  }
  v15 = -2147467259;
  if ( *((_DWORD *)this + 2) )
  {
    v16 = *((_DWORD *)this + 2);
    if ( v16 != GetCurrentThreadId() )
    {
      ErrOut(L"Kernel transport in use, packet write failed\n");
      return v15;
    }
  }
  v17 = 0;
  v18 = PacketTypeToPacketName((unsigned __int16)v13);
  KdOut(L"WRITE: Write type %s packet\n", v18);
  if ( *(_BYTE *)(*((_QWORD *)this + 8) + 45LL) || (_DWORD)v13 != 2 )
  {
    v20 = v39;
  }
  else
  {
    v20 = DbgkdManipulateState64To32(a2, v46);
    v39 = v20;
    v41 = (unsigned __int8 *)v46;
    if ( LODWORD(v46[0]) == 12615 )
    {
      v21 = (unsigned __int8 *)malloc((unsigned __int64)a6 >> 1);
      v17 = v21;
      if ( !v21 )
      {
        ErrOut(L"Failed to allocate Packet Data\n");
        return v15;
      }
      v22 = (int *)v46;
      v19 = a6 >> 3;
      v23 = v21;
      if ( (_DWORD)v19 )
      {
        do
        {
          v24 = *v22;
          v22 += 2;
          *(_DWORD *)v23 = v24;
          v23 += 4;
          v25 = (_DWORD)v19 == 1;
          v19 = (unsigned int)(v19 - 1);
        }
        while ( !v25 );
      }
      v8 = v17;
      v9 = a6 >> 1;
      v26 = 0;
      goto LABEL_19;
    }
  }
  v26 = 0;
  if ( a5 )
LABEL_19:
    KdConnection::ComputeChecksum((KdConnection *)v19, v8, v9);
  v27 = KdConnection::ComputeChecksum((KdConnection *)v19, v41, v20);
  v42 = 808464432;
  v29 = g_PacketLogIndex;
  HIDWORD(v45) = v27 + v30;
  ++g_PacketLogIndex;
  v44 = v31;
  v43 = v13;
  *((_DWORD *)this + 7) = 0;
  v25 = (g_EngStatus & 0x800) == 0;
  (&g_PacketLog)[v29 & 0xF] = (unsigned __int64 near *)(v31 | (unsigned __int64)(v13 << 32) | 0xF000000000000000uLL);
  v40 = 0;
  if ( v25 )
  {
    v32 = 1;
    while ( 1 )
    {
      v33 = DbgKdTransport::WritePacketContents(this, (struct _KD_PACKET *)&v42, v41, v28, v8, v9, v26, v38);
      v15 = v33;
      if ( !v33 )
        break;
      if ( v33 == -805306054 )
        goto LABEL_44;
      if ( (v33 & 0x1FFF0000) == 0x10000 )
      {
        v36 = FormatStatusCode(v33);
        ErrOut(L"KD remote connection lost, %s\n", v36);
        goto LABEL_44;
      }
      v34 = v26 & 3;
      if ( v34 != 3 )
        v26 = (v34 + 1) | v26 & 0xFFFFFFFC;
      if ( a8 )
      {
        if ( v15 == 10049 && *a8 - 5 <= 1 && (unsigned int)++v40 > 5 )
        {
          v35 = FormatStatusCode(10049);
          ErrOut(
            L"Cannot write on the current requested socket/address.This normally results from an attempt to bind ",
            L"to an address that is not valid for the local computer. %s\n",
            v35);
          goto LABEL_44;
        }
      }
      Sleep(0xAu);
      if ( (++*((_DWORD *)this + 7) & 0x3F) == 0 )
      {
        WarnOut(L"... Retry sending the same data packet for %lu times.\n");
        if ( *((_DWORD *)this + 7) == 64 && (g_KdTransportIndex == 6 || g_KdTransportIndex == 5) )
          FeatureUsageTracker::FeatureUsed(L"KDNET", L"ErrRetrySending", 5u);
        if ( v32 )
        {
          WarnOut(
            L"The transport connection between host kernel debugger and target Windows seems lost.\n"
             "please try resync with target, recycle the host debugger, or reboot the target Windows.\n");
          v32 = 0;
        }
      }
      if ( (g_EngStatus & 0x800) != 0 )
        goto LABEL_43;
      v28 = v39;
    }
    ++*((_DWORD *)this + 147);
  }
  else
  {
LABEL_43:
    KdOut(L"WriteDataPacket interrupted by exit request\n");
  }
LABEL_44:
  if ( v17 )
    free(v17);
  return v15;
}

```

## disassembly

```asm
0x1801d11e0  push    rbp
0x1801d11e2  push    rbx
0x1801d11e3  push    rsi
0x1801d11e4  push    rdi
0x1801d11e5  push    r12
0x1801d11e7  push    r13
0x1801d11e9  push    r14
0x1801d11eb  push    r15
0x1801d11ed  lea     rbp, [rsp-7]
0x1801d11f2  sub     rsp, 0B8h
0x1801d11f9  mov     rax, cs:__security_cookie
0x1801d1200  xor     rax, rsp
0x1801d1203  mov     [rbp+3Fh+var_50], rax
0x1801d1207  mov     r13, [rbp+3Fh+arg_20]
0x1801d120b  xor     eax, eax
0x1801d120d  movzx   r15d, [rbp+3Fh+arg_28]
0x1801d1212  xorps   xmm0, xmm0
0x1801d1215  mov     [rbp+3Fh+var_58], eax
0x1801d1218  mov     rdi, rcx
0x1801d121b  mov     rax, [rcx+40h]
0x1801d121f  mov     r12, rdx
0x1801d1222  movups  [rbp+3Fh+var_88], xmm0
0x1801d1226  movzx   r14d, r9w
0x1801d122a  movups  [rbp+3Fh+var_78], xmm0
0x1801d122e  mov     word ptr [rbp+3Fh+var_AC], r8w
0x1801d1233  movups  [rbp+3Fh+var_68], xmm0
0x1801d1237  mov     ecx, [rax+1080h]
0x1801d123d  mov     [rbp+3Fh+var_A0], rdx
0x1801d1241  mov     [rbp+3Fh+var_90], 0
0x1801d1249  test    ecx, ecx
0x1801d124b  jnz     short loc_1801D1257
0x1801d124d  cmp     r14d, 0Ch
0x1801d1251  jb      short loc_1801D1261
0x1801d1253  test    ecx, ecx
0x1801d1255  jz      short loc_1801D125C
0x1801d1257  cmp     r14d, ecx
0x1801d125a  jb      short loc_1801D1261
0x1801d125c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1801d1261  cmp     dword ptr [rdi+8], 0
0x1801d1265  mov     esi, 80004005h
0x1801d126a  jz      short loc_1801D1290
0x1801d126c  mov     ebx, [rdi+8]
0x1801d126f  call    cs:__imp_GetCurrentThreadId
0x1801d1276  nop     dword ptr [rax+rax+00h]
0x1801d127b  cmp     ebx, eax
0x1801d127d  jz      short loc_1801D1290
0x1801d127f  lea     rcx, aKernelTranspor; "Kernel transport in use, packet write f"...
0x1801d1286  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1801d128b  jmp     loc_1801D154E
0x1801d1290  movzx   ecx, r14w
0x1801d1294  xor     ebx, ebx
0x1801d1296  call    PacketTypeToPacketName
0x1801d129b  mov     rdx, rax
0x1801d129e  lea     rcx, aWriteWriteType; "WRITE: Write type %s packet\n"
0x1801d12a5  call    ?KdOut@@YAXPEBGZZ; KdOut(ushort const *,...)
0x1801d12aa  mov     rax, [rdi+40h]
0x1801d12ae  cmp     [rax+2Dh], bl
0x1801d12b1  jnz     short loc_1801D1332
0x1801d12b3  cmp     r14d, 2
0x1801d12b7  jnz     short loc_1801D1332
0x1801d12b9  lea     rdx, [rbp+3Fh+var_88]
0x1801d12bd  mov     rcx, r12
0x1801d12c0  call    DbgkdManipulateState64To32
0x1801d12c5  cmp     dword ptr [rbp+3Fh+var_88], 3147h
0x1801d12cc  mov     r11d, eax
0x1801d12cf  mov     [rbp+3Fh+var_AC], eax
0x1801d12d2  lea     rax, [rbp+3Fh+var_88]
0x1801d12d6  mov     [rbp+3Fh+var_A0], rax
0x1801d12da  jnz     short loc_1801D1336
0x1801d12dc  mov     rcx, r15
0x1801d12df  shr     rcx, 1; Size
0x1801d12e2  call    cs:__imp_malloc
0x1801d12e9  nop     dword ptr [rax+rax+00h]
0x1801d12ee  mov     rbx, rax
0x1801d12f1  test    rax, rax
0x1801d12f4  jnz     short loc_1801D12FF
0x1801d12f6  lea     rcx, aFailedToAlloca_0; "Failed to allocate Packet Data\n"
0x1801d12fd  jmp     short loc_1801D1286
0x1801d12ff  mov     ecx, r15d
0x1801d1302  lea     r8, [rbp+3Fh+var_88]
0x1801d1306  shr     ecx, 3
0x1801d1309  mov     rdx, rbx
0x1801d130c  test    ecx, ecx
0x1801d130e  jz      short loc_1801D1322
0x1801d1310  mov     eax, [r8]
0x1801d1313  lea     r8, [r8+8]
0x1801d1317  mov     [rdx], eax
0x1801d1319  lea     rdx, [rdx+4]
0x1801d131d  add     ecx, 0FFFFFFFFh
0x1801d1320  jnz     short loc_1801D1310
0x1801d1322  mov     r11d, [rbp+3Fh+var_AC]
0x1801d1326  mov     r13, rbx
0x1801d1329  shr     r15w, 1
0x1801d132d  xor     r12d, r12d
0x1801d1330  jmp     short loc_1801D133E
0x1801d1332  mov     r11d, [rbp+3Fh+var_AC]
0x1801d1336  xor     r12d, r12d
0x1801d1339  test    r13, r13
0x1801d133c  jz      short loc_1801D1353
0x1801d133e  movzx   r8d, r15w; unsigned int
0x1801d1342  lea     r9d, [r11+r15]
0x1801d1346  mov     rdx, r13; unsigned __int8 *
0x1801d1349  call    ?ComputeChecksum@KdConnection@@QEAAKPEAEK@Z; KdConnection::ComputeChecksum(uchar *,ulong)
0x1801d134e  mov     r10d, eax
0x1801d1351  jmp     short loc_1801D135A
0x1801d1353  movzx   r9d, r11w
0x1801d1357  xor     r10d, r10d
0x1801d135a  mov     rdx, [rbp+3Fh+var_A0]; unsigned __int8 *
0x1801d135e  movzx   r8d, r11w; unsigned int
0x1801d1362  call    ?ComputeChecksum@KdConnection@@QEAAKPEAEK@Z; KdConnection::ComputeChecksum(uchar *,ulong)
0x1801d1367  add     r10d, eax
0x1801d136a  mov     [rbp+3Fh+var_98], 30303030h
0x1801d1371  mov     eax, cs:?g_PacketLogIndex@@3KA; ulong g_PacketLogIndex
0x1801d1377  mov     rcx, r14
0x1801d137a  mov     edx, eax
0x1801d137c  shl     rcx, 20h
0x1801d1380  inc     eax
0x1801d1382  mov     dword ptr [rbp+3Fh+var_90+4], r10d
0x1801d1386  mov     cs:?g_PacketLogIndex@@3KA, eax; ulong g_PacketLogIndex
0x1801d138c  and     edx, 0Fh
0x1801d138f  movzx   eax, r9w
0x1801d1393  or      rcx, rax
0x1801d1396  mov     [rbp+3Fh+var_92], r9w
0x1801d139b  mov     rax, 0F000000000000000h
0x1801d13a5  mov     [rbp+3Fh+var_94], r14w
0x1801d13aa  or      rcx, rax
0x1801d13ad  mov     dword ptr [rdi+1Ch], 0
0x1801d13b4  test    cs:?g_EngStatus@@3KA, 800h; ulong g_EngStatus
0x1801d13be  lea     rax, ?g_PacketLog@@3PA_KA; unsigned __int64 near * g_PacketLog
0x1801d13c5  mov     [rax+rdx*8], rcx
0x1801d13c9  mov     [rbp+3Fh+var_A8], 0
0x1801d13d0  jnz     loc_1801D152E
0x1801d13d6  mov     r14b, 1
0x1801d13d9  mov     r8, [rbp+3Fh+var_A0]; void *
0x1801d13dd  lea     rdx, [rbp+3Fh+var_98]; struct _KD_PACKET *
0x1801d13e1  mov     [rsp+0F0h+var_C0], r12d; unsigned int
0x1801d13e6  movzx   r9d, r11w; unsigned __int16
0x1801d13ea  mov     [rsp+0F0h+var_C8], r15w; unsigned __int16
0x1801d13f0  mov     rcx, rdi; this
0x1801d13f3  mov     [rsp+0F0h+var_D0], r13; void *
0x1801d13f8  call    ?WritePacketContents@DbgKdTransport@@QEAAJPEAU_KD_PACKET@@PEAXG1GKH@Z; DbgKdTransport::WritePacketContents(_KD_PACKET *,void *,ushort,void *,ushort,ulong,int)
0x1801d13fd  mov     esi, eax
0x1801d13ff  test    eax, eax
0x1801d1401  jz      loc_1801D1526
0x1801d1407  cmp     eax, 0D000013Ah
0x1801d140c  jz      loc_1801D153A
0x1801d1412  mov     ecx, eax
0x1801d1414  and     ecx, 1FFF0000h
0x1801d141a  cmp     ecx, 10000h
0x1801d1420  jz      loc_1801D150E
0x1801d1426  mov     eax, r12d
0x1801d1429  and     eax, 3
0x1801d142c  cmp     eax, 3
0x1801d142f  jz      short loc_1801D143A
0x1801d1431  inc     eax
0x1801d1433  and     r12d, 0FFFFFFFCh
0x1801d1437  or      r12d, eax
0x1801d143a  mov     rax, [rbp+3Fh+arg_38]
0x1801d1441  test    rax, rax
0x1801d1444  jz      short loc_1801D146A
0x1801d1446  mov     ecx, 2741h; int
0x1801d144b  cmp     esi, ecx
0x1801d144d  jnz     short loc_1801D146A
0x1801d144f  mov     eax, [rax]
0x1801d1451  sub     eax, 5
0x1801d1454  cmp     eax, 1
0x1801d1457  ja      short loc_1801D146A
0x1801d1459  mov     eax, [rbp+3Fh+var_A8]
0x1801d145c  inc     eax
0x1801d145e  mov     [rbp+3Fh+var_A8], eax
0x1801d1461  cmp     eax, 5
0x1801d1464  ja      loc_1801D14F1
0x1801d146a  mov     ecx, 0Ah; dwMilliseconds
0x1801d146f  call    cs:__imp_Sleep
0x1801d1476  nop     dword ptr [rax+rax+00h]
0x1801d147b  inc     dword ptr [rdi+1Ch]
0x1801d147e  mov     edx, [rdi+1Ch]
0x1801d1481  test    dl, 3Fh
0x1801d1484  jnz     short loc_1801D14DC
0x1801d1486  lea     rcx, aRetrySendingTh; "... Retry sending the same data packet "...
0x1801d148d  call    ?WarnOut@@YAXPEBGZZ; WarnOut(ushort const *,...)
0x1801d1492  cmp     dword ptr [rdi+1Ch], 40h ; '@'
0x1801d1496  jnz     short loc_1801D14C3
0x1801d1498  mov     eax, cs:g_KdTransportIndex
0x1801d149e  cmp     eax, 6
0x1801d14a1  jz      short loc_1801D14AA
0x1801d14a3  dec     eax
0x1801d14a5  cmp     eax, 4
0x1801d14a8  jnz     short loc_1801D14C3
0x1801d14aa  mov     r8d, 5; unsigned int
0x1801d14b0  lea     rdx, aErrretrysendin; "ErrRetrySending"
0x1801d14b7  lea     rcx, aKdnet_0; "KDNET"
0x1801d14be  call    ?FeatureUsed@FeatureUsageTracker@@SAXQEBG0K@Z; FeatureUsageTracker::FeatureUsed(ushort const * const,ushort const * const,ulong)
0x1801d14c3  test    r14b, r14b
0x1801d14c6  jz      short loc_1801D14DC
0x1801d14c8  lea     rcx, aTheTransportCo; "The transport connection between host k"...
0x1801d14cf  mov     [rbp+3Fh+var_B0], 0
0x1801d14d3  call    ?WarnOut@@YAXPEBGZZ; WarnOut(ushort const *,...)
0x1801d14d8  mov     r14b, [rbp+3Fh+var_B0]
0x1801d14dc  test    cs:?g_EngStatus@@3KA, 800h; ulong g_EngStatus
0x1801d14e6  jnz     short loc_1801D152E
0x1801d14e8  mov     r11d, [rbp+3Fh+var_AC]
0x1801d14ec  jmp     loc_1801D13D9
0x1801d14f1  call    ?FormatStatusCode@@YAPEAGJ@Z; FormatStatusCode(long)
0x1801d14f6  mov     r8, rax
0x1801d14f9  lea     rdx, aToAnAddressTha; "to an address that is not valid for the"...
0x1801d1500  lea     rcx, aCannotWriteOnT; "Cannot write on the current requested s"...
0x1801d1507  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1801d150c  jmp     short loc_1801D153A
0x1801d150e  mov     ecx, esi; int
0x1801d1510  call    ?FormatStatusCode@@YAPEAGJ@Z; FormatStatusCode(long)
0x1801d1515  mov     rdx, rax
0x1801d1518  lea     rcx, aKdRemoteConnec; "KD remote connection lost, %s\n"
0x1801d151f  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1801d1524  jmp     short loc_1801D153A
0x1801d1526  inc     dword ptr [rdi+24Ch]
0x1801d152c  jmp     short loc_1801D153A
0x1801d152e  lea     rcx, aWritedatapacke; "WriteDataPacket interrupted by exit req"...
0x1801d1535  call    ?KdOut@@YAXPEBGZZ; KdOut(ushort const *,...)
0x1801d153a  test    rbx, rbx
0x1801d153d  jz      short loc_1801D154E
0x1801d153f  mov     rcx, rbx; Block
0x1801d1542  call    cs:__imp_free
0x1801d1549  nop     dword ptr [rax+rax+00h]
0x1801d154e  mov     eax, esi
0x1801d1550  mov     rcx, [rbp+3Fh+var_50]
0x1801d1554  xor     rcx, rsp; StackCookie
0x1801d1557  call    __security_check_cookie
0x1801d155c  add     rsp, 0B8h
0x1801d1563  pop     r15
0x1801d1565  pop     r14
0x1801d1567  pop     r13
0x1801d1569  pop     r12
0x1801d156b  pop     rdi
0x1801d156c  pop     rsi
0x1801d156d  pop     rbx
0x1801d156e  pop     rbp
0x1801d156f  retn
```
