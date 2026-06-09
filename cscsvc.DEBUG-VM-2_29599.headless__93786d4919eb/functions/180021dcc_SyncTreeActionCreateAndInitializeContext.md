# SyncTreeActionCreateAndInitializeContext

- ea: `0x180021dcc`
- end: `0x1800222ff`
- name: `SyncTreeActionCreateAndInitializeContext`
- size: `1331`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x180021040`

## callees

- `0x1800153f0`
- `0x180018dd0`
- `0x18001dea0`
- `0x180021dcc`
- `0x180023650`
- `0x18002a524`
- `0x180032700`
- `0x1800360c0`
- `0x180036394`
- `0x180039610`
- `0x180039fb4`
- `0x18003c460`
- `0x1800469c0`
- `0x18007291c`
- `0x1800743dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021fe7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021fe7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002202c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002202c`
- `KERNEL32!VirtualFree` at `0x180022298`
- `KERNEL32!VirtualFree` at `0x180022298`

## string_xrefs

- `0x180021e53`: `SyncTreeActionCreateAndInitializeContext: SC: 0x%p PC: 0x%p NewContext: 0x%p Flags: 0x%x`
- `0x180022249`: `SyncTreeActionNewContext: SyncOpenFileRelative failed with %x`
- `0x180021f39`: `SyncTreeActionNewContext: SyncTreeNewTempNode failed with %x`
- `0x1800221d1`: `SyncTreeActionCreateAndInitializeContext: SyncStatus [%x]  Client: %d  Server: %d`
- `0x1800222b2`: `SyncTreeActionCreateAndInitializeContext: %x`

## pseudocode

```c
__int64 __fastcall SyncTreeActionCreateAndInitializeContext(__int64 a1, _QWORD *a2, LPVOID *a3, int a4)
{
  int v8; // r15d
  unsigned int v9; // esi
  __int64 v10; // r13
  int v11; // r15d
  __int64 v12; // r8
  CObjectMonitor *v13; // rax
  int *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // r11
  int *v17; // rcx
  __int64 v18; // rcx
  int v19; // r15d
  __int64 v20; // r9
  __int64 v21; // rax
  __int64 v22; // r8
  int v23; // edx
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rdx
  int v26; // r9d
  int v27; // r8d
  __int128 *v28; // rcx
  __int64 v29; // rax
  int v30; // edx
  int v31; // r14d
  __int64 v32; // rcx
  LPVOID lpAddress; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v35; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v36; // [rsp+58h] [rbp-A8h]
  _DWORD v37[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v38; // [rsp+78h] [rbp-88h]
  __int64 v39; // [rsp+80h] [rbp-80h]
  __int64 v40; // [rsp+88h] [rbp-78h]
  int v41; // [rsp+90h] [rbp-70h]
  int v42; // [rsp+94h] [rbp-6Ch]

  lpAddress = 0;
  v37[1] = 0;
  memset_0(v37, 0, 0x7Cu);
  v8 = *(_DWORD *)(a1 + 8);
  v35 = 0;
  v36 = 0;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
  {
    SyncTraceOutputInternal(
      L"SyncTreeActionCreateAndInitializeContext: SC: 0x%p PC: 0x%p NewContext: 0x%p Flags: 0x%x",
      a1,
      a2,
      a3,
      a4);
    WPP_SF_qqqD(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      15,
      WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids,
      a1,
      a2,
      a3,
      a4);
  }
  *a3 = 0;
  v9 = SyncTreeActionNewContext(&lpAddress, a2 + 1030, a2[4] + 68LL, *(unsigned int *)(a2[4] + 60LL));
  if ( v9 || !lpAddress )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(L"SyncTreeActionNewContext: SyncOpenFileRelative failed with %x", v9);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 16, WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids, v9);
      v13 = WPP_GLOBAL_Control;
    }
    if ( !v9 )
      goto LABEL_47;
    goto LABEL_44;
  }
  *(_QWORD *)lpAddress = a2;
  *((_DWORD *)lpAddress + 11) = 1;
  v10 = *(_DWORD *)(a2[4] + 60LL) >> 1;
  v11 = v8 & 0x400;
  v12 = (unsigned int)(2 * v10 + 218);
  if ( !v11 )
    v12 = (unsigned int)(2 * v10 + 154);
  v9 = SyncTreeNewTempNode((char *)lpAddress + 16, a2[2], v12);
  if ( v9 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(L"SyncTreeActionNewContext: SyncTreeNewTempNode failed with %x", v9);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 17, WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids, v9);
      v13 = WPP_GLOBAL_Control;
    }
    goto LABEL_44;
  }
  v14 = (int *)*((_QWORD *)lpAddress + 2);
  if ( (*v14 & 0x20000000) != 0 )
  {
    v15 = 36;
  }
  else
  {
    v15 = 34;
    if ( *v14 < 0 )
      v15 = 9;
  }
  StringCchCopyNW(
    (STRSAFE_LPWSTR)&v14[v15],
    (unsigned int)(v10 + 1),
    (STRSAFE_PCNZWCH)(a2[4] + 68LL),
    (unsigned __int64)*(unsigned int *)(a2[4] + 60LL) >> 1);
  v17 = (int *)*((_QWORD *)lpAddress + 2);
  if ( (*v17 & 0x20000000) == 0 )
  {
    v16 = 136;
    if ( *v17 < 0 )
      v16 = 36;
  }
  *(_WORD *)((char *)v17 + 2 * v10 + v16) = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 32));
  v18 = a2[3];
  if ( v18 )
    *(_QWORD *)(v18 + 16) = *((_QWORD *)lpAddress + 2);
  else
    *(_QWORD *)(a2[2] + 8LL) = *((_QWORD *)lpAddress + 2);
  if ( v11 )
    SyncItemTraceInitialize(*((_QWORD *)lpAddress + 2), (unsigned int)(v10 + 1));
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 32));
  a2[3] = *((_QWORD *)lpAddress + 2);
  memset_0(v37, 0, 0x80u);
  v19 = a4 & 0x10000000;
  if ( (a4 & 0x10000000) == 0 )
  {
LABEL_34:
    v31 = a4 & 0x20000000;
    if ( v31 )
    {
      v32 = a2[4];
      *(_QWORD *)&v35 = *(_QWORD *)(v32 + 40);
      *(_QWORD *)&v36 = *(_QWORD *)(v32 + 24);
      *((_QWORD *)&v35 + 1) = *(_QWORD *)(v32 + 32);
      DWORD2(v36) = *(_DWORD *)(v32 + 56);
      SyncItemAddServerEnumInfo(&v35, 0, v37);
    }
    SyncItemPatchChangeDescriptors(v37, *((_QWORD *)lpAddress + 2), 0, 0);
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
    {
      SyncTraceOutputInternal(
        L"SyncTreeActionCreateAndInitializeContext: SyncStatus [%x]  Client: %d  Server: %d",
        **((unsigned int **)lpAddress + 2),
        v19 != 0,
        v31 != 0);
      WPP_SF_DDD(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        19,
        WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids,
        **((unsigned int **)lpAddress + 2),
        v19 != 0,
        v31 != 0);
    }
    *a3 = lpAddress;
    goto LABEL_46;
  }
  v20 = a2[4];
  v21 = *(_QWORD *)(v20 + 32);
  v22 = *(_QWORD *)(v20 + 24);
  v23 = *(_DWORD *)(v20 + 56) & 0x4017;
  v38 = *(_QWORD *)(v20 + 40);
  v39 = v21;
  v41 = v23;
  v42 = HIDWORD(v36);
  v37[0] = 589824;
  v40 = v22;
  v24 = ((unsigned int)(*(_DWORD *)(v20 + 60) + 68) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
  if ( *(_DWORD *)(v24 + v20) == 1542600881 )
  {
    v25 = v24 + v20 + 8;
    if ( v25 )
    {
      v26 = v25 + 72;
      DWORD2(v36) = *(_DWORD *)(v25 + 64);
      v27 = v25 + 4;
      v28 = &v35;
      *(_QWORD *)&v36 = *(_QWORD *)(v25 + 32);
      *((_QWORD *)&v35 + 1) = *(_QWORD *)(v25 + 40);
      v29 = *(_QWORD *)(v25 + 56);
      v30 = *(_DWORD *)v25;
      *(_QWORD *)&v35 = v29;
    }
    else
    {
      v26 = 0;
      v27 = 0;
      v30 = 0;
      LODWORD(v28) = 0;
    }
    SyncItemAddOriginalEnumInfo((_DWORD)v28, v30, v27, v26, (__int64)v37);
    goto LABEL_34;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    SyncTraceOutputInternal(L"SyncTreeActionNewContext: item does not have a valid cookie");
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 18, WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids);
    v13 = WPP_GLOBAL_Control;
  }
  v9 = -1073740768;
LABEL_44:
  if ( lpAddress )
  {
    ++NumLargeFree;
    VirtualFree(lpAddress, 0, 0x8000u);
LABEL_46:
    v13 = WPP_GLOBAL_Control;
  }
LABEL_47:
  if ( v13 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v13 + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"SyncTreeActionCreateAndInitializeContext: %x", v9);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 20, WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids, v9);
  }
  return v9;
}

```

## disassembly

```asm
0x180021dcc  push    rbp
0x180021dce  push    rbx
0x180021dcf  push    rsi
0x180021dd0  push    rdi
0x180021dd1  push    r12
0x180021dd3  push    r13
0x180021dd5  push    r14
0x180021dd7  push    r15
0x180021dd9  lea     rbp, [rsp-8]
0x180021dde  sub     rsp, 108h
0x180021de5  mov     rax, cs:__security_cookie
0x180021dec  xor     rax, rsp
0x180021def  mov     [rbp+40h+var_50], rax
0x180021df3  xor     eax, eax
0x180021df5  mov     [rsp+140h+lpAddress], 0
0x180021dfe  mov     r12, r8
0x180021e01  mov     [rsp+140h+var_CC], eax
0x180021e05  mov     rbx, rdx
0x180021e08  mov     rdi, rcx
0x180021e0b  xor     edx, edx; Val
0x180021e0d  lea     rcx, [rsp+140h+var_D0]; void *
0x180021e12  lea     r8d, [rax+7Ch]; Size
0x180021e16  mov     r14d, r9d
0x180021e19  call    memset_0
0x180021e1e  mov     r15d, [rdi+8]
0x180021e22  xorps   xmm0, xmm0
0x180021e25  movups  [rsp+140h+var_F8], xmm0
0x180021e2a  movups  [rsp+140h+var_E8], xmm0
0x180021e2f  mov     rax, cs:WPP_GLOBAL_Control
0x180021e36  lea     r13, WPP_GLOBAL_Control
0x180021e3d  cmp     rax, r13
0x180021e40  jz      short loc_180021E90
0x180021e42  test    byte ptr [rax+6Ch], 4
0x180021e46  jz      short loc_180021E90
0x180021e48  mov     r9, r12
0x180021e4b  mov     dword ptr [rsp+140h+var_120], r14d
0x180021e50  mov     r8, rbx
0x180021e53  lea     rcx, aSynctreeaction_17; "SyncTreeActionCreateAndInitializeContex"...
0x180021e5a  mov     rdx, rdi
0x180021e5d  call    SyncTraceOutputInternal
0x180021e62  mov     rcx, cs:WPP_GLOBAL_Control
0x180021e69  lea     r8, WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids
0x180021e70  mov     [rsp+140h+var_110], r14d
0x180021e75  mov     edx, 0Fh
0x180021e7a  mov     [rsp+140h+var_118], r12
0x180021e7f  mov     r9, rdi
0x180021e82  mov     [rsp+140h+var_120], rbx
0x180021e87  mov     rcx, [rcx+60h]
0x180021e8b  call    WPP_SF_qqqD
0x180021e90  mov     qword ptr [r12], 0
0x180021e98  lea     rdx, [rbx+2030h]
0x180021e9f  mov     r9, [rbx+20h]
0x180021ea3  lea     rcx, [rsp+140h+lpAddress]
0x180021ea8  lea     r8, [r9+44h]
0x180021eac  mov     r9d, [r9+3Ch]
0x180021eb0  call    SyncTreeActionNewContext
0x180021eb5  mov     esi, eax
0x180021eb7  test    eax, eax
0x180021eb9  jnz     loc_180022235
0x180021ebf  mov     rcx, [rsp+140h+lpAddress]
0x180021ec4  test    rcx, rcx
0x180021ec7  jz      loc_180022235
0x180021ecd  mov     [rcx], rbx
0x180021ed0  mov     rax, [rsp+140h+lpAddress]
0x180021ed5  mov     dword ptr [rax+2Ch], 1
0x180021edc  mov     rax, [rbx+20h]
0x180021ee0  mov     rcx, [rsp+140h+lpAddress]
0x180021ee5  mov     rdx, [rbx+10h]
0x180021ee9  mov     r13d, [rax+3Ch]
0x180021eed  shr     r13d, 1
0x180021ef0  and     r15d, 400h
0x180021ef7  lea     eax, ds:9Ah[r13*2]
0x180021eff  lea     r8d, [rax+40h]
0x180021f03  cmovz   r8d, eax
0x180021f07  add     rcx, 10h
0x180021f0b  call    SyncTreeNewTempNode
0x180021f10  mov     esi, eax
0x180021f12  test    eax, eax
0x180021f14  jz      short loc_180021F70
0x180021f16  mov     rax, cs:WPP_GLOBAL_Control
0x180021f1d  lea     r13, WPP_GLOBAL_Control
0x180021f24  cmp     rax, r13
0x180021f27  jz      loc_18002227F
0x180021f2d  test    byte ptr [rax+6Ch], 1
0x180021f31  jz      loc_18002227F
0x180021f37  mov     edx, esi
0x180021f39  lea     rcx, aSynctreeaction_1; "SyncTreeActionNewContext: SyncTreeNewTe"...
0x180021f40  call    SyncTraceOutputInternal
0x180021f45  mov     rcx, cs:WPP_GLOBAL_Control
0x180021f4c  lea     r8, WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids
0x180021f53  mov     edx, 11h
0x180021f58  mov     r9d, esi
0x180021f5b  mov     rcx, [rcx+60h]
0x180021f5f  call    WPP_SF_d
0x180021f64  mov     rax, cs:WPP_GLOBAL_Control
0x180021f6b  jmp     loc_18002227F
0x180021f70  mov     rax, [rsp+140h+lpAddress]
0x180021f75  mov     edx, 24h ; '$'
0x180021f7a  mov     rcx, [rax+10h]
0x180021f7e  lea     r11d, [rdx+6Ch]
0x180021f82  test    dword ptr [rcx], 20000000h
0x180021f88  jz      short loc_180021F8F
0x180021f8a  mov     eax, r11d
0x180021f8d  jmp     short loc_180021F9B
0x180021f8f  cmp     dword ptr [rcx], 0
0x180021f92  mov     eax, 88h
0x180021f97  cmovl   rax, rdx
0x180021f9b  mov     r8, [rbx+20h]
0x180021f9f  lea     edx, [r13+1]; cchDest
0x180021fa3  add     rcx, rax; pszDest
0x180021fa6  mov     r9d, [r8+3Ch]
0x180021faa  add     r8, 44h ; 'D'; pszSrc
0x180021fae  shr     r9, 1; cchToCopy
0x180021fb1  call    StringCchCopyNW
0x180021fb6  mov     r10, [rsp+140h+lpAddress]
0x180021fbb  mov     rcx, [r10+10h]
0x180021fbf  test    dword ptr [rcx], 20000000h
0x180021fc5  jnz     short loc_180021FD8
0x180021fc7  cmp     dword ptr [rcx], 0
0x180021fca  mov     r11d, 88h
0x180021fd0  lea     eax, [r11-64h]
0x180021fd4  cmovl   r11d, eax
0x180021fd8  lea     rcx, [rcx+r13*2]
0x180021fdc  xor     eax, eax
0x180021fde  mov     [rcx+r11], ax
0x180021fe3  lea     rcx, [rdi+20h]; lpCriticalSection
0x180021fe7  call    cs:__imp_EnterCriticalSection
0x180021fed  mov     rcx, [rbx+18h]
0x180021ff1  mov     rax, [rsp+140h+lpAddress]
0x180021ff6  test    rcx, rcx
0x180021ff9  jnz     short loc_180022009
0x180021ffb  mov     rdx, [rbx+10h]
0x180021fff  mov     rcx, [rax+10h]
0x180022003  mov     [rdx+8], rcx
0x180022007  jmp     short loc_180022011
0x180022009  mov     r8, [rax+10h]
0x18002200d  mov     [rcx+10h], r8
0x180022011  test    r15d, r15d
0x180022014  jz      short loc_180022028
0x180022016  mov     rcx, [rsp+140h+lpAddress]
0x18002201b  lea     edx, [r13+1]
0x18002201f  mov     rcx, [rcx+10h]
0x180022023  call    SyncItemTraceInitialize
0x180022028  lea     rcx, [rdi+20h]; lpCriticalSection
0x18002202c  call    cs:__imp_LeaveCriticalSection
0x180022032  mov     rax, [rsp+140h+lpAddress]
0x180022037  xor     edx, edx; Val
0x180022039  mov     r8d, 80h; Size
0x18002203f  mov     rcx, [rax+10h]
0x180022043  mov     [rbx+18h], rcx
0x180022047  lea     rcx, [rsp+140h+var_D0]; void *
0x18002204c  call    memset_0
0x180022051  mov     r15d, r14d
0x180022054  and     r15d, 10000000h
0x18002205b  jz      loc_18002215A
0x180022061  mov     r9, [rbx+20h]
0x180022065  mov     rcx, [r9+28h]
0x180022069  mov     rax, [r9+20h]
0x18002206d  mov     edx, [r9+38h]
0x180022071  mov     r8, [r9+18h]
0x180022075  and     edx, 4017h
0x18002207b  mov     [rsp+140h+var_C8], rcx
0x180022080  mov     [rbp+40h+var_C0], rax
0x180022084  mov     eax, dword ptr [rsp+140h+var_E8+0Ch]
0x180022088  mov     [rbp+40h+var_B0], edx
0x18002208b  mov     [rbp+40h+var_AC], eax
0x18002208e  mov     [rsp+140h+var_D0], 90000h
0x180022096  mov     [rbp+40h+var_B8], r8
0x18002209a  mov     ecx, [r9+3Ch]
0x18002209e  add     ecx, 44h ; 'D'
0x1800220a1  add     rcx, 7
0x1800220a5  and     rcx, 0FFFFFFFFFFFFFFF8h
0x1800220a9  cmp     dword ptr [rcx+r9], 5BF238B1h
0x1800220b1  jz      short loc_180022105
0x1800220b3  mov     rax, cs:WPP_GLOBAL_Control
0x1800220ba  lea     r13, WPP_GLOBAL_Control
0x1800220c1  cmp     rax, r13
0x1800220c4  jz      short loc_1800220FB
0x1800220c6  test    byte ptr [rax+6Ch], 1
0x1800220ca  jz      short loc_1800220FB
0x1800220cc  lea     rcx, aSynctreeaction; "SyncTreeActionNewContext: item does not"...
0x1800220d3  call    SyncTraceOutputInternal
0x1800220d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800220df  lea     r8, WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids
0x1800220e6  mov     edx, 12h
0x1800220eb  mov     rcx, [rcx+60h]
0x1800220ef  call    WPP_SF_
0x1800220f4  mov     rax, cs:WPP_GLOBAL_Control
0x1800220fb  mov     esi, 0C0000420h
0x180022100  jmp     loc_18002227F
0x180022105  lea     rdx, [r9+8]
0x180022109  add     rdx, rcx
0x18002210c  jz      short loc_180022141
0x18002210e  mov     eax, [rdx+40h]
0x180022111  lea     r9, [rdx+48h]
0x180022115  mov     dword ptr [rsp+140h+var_E8+8], eax
0x180022119  lea     r8, [rdx+4]
0x18002211d  mov     rax, [rdx+20h]
0x180022121  lea     rcx, [rsp+140h+var_F8]
0x180022126  mov     qword ptr [rsp+140h+var_E8], rax
0x18002212b  mov     rax, [rdx+28h]
0x18002212f  mov     qword ptr [rsp+140h+var_F8+8], rax
0x180022134  mov     rax, [rdx+38h]
0x180022138  mov     edx, [rdx]
0x18002213a  mov     qword ptr [rsp+140h+var_F8], rax
0x18002213f  jmp     short loc_18002214B
0x180022141  xor     r9d, r9d
0x180022144  xor     r8d, r8d
0x180022147  xor     edx, edx
0x180022149  xor     ecx, ecx
0x18002214b  lea     rax, [rsp+140h+var_D0]
0x180022150  mov     [rsp+140h+var_120], rax
0x180022155  call    SyncItemAddOriginalEnumInfo
0x18002215a  and     r14d, 20000000h
0x180022161  jz      short loc_18002219A
0x180022163  mov     rcx, [rbx+20h]
0x180022167  lea     r8, [rsp+140h+var_D0]
0x18002216c  xor     edx, edx
0x18002216e  mov     rax, [rcx+28h]
0x180022172  mov     qword ptr [rsp+140h+var_F8], rax
0x180022177  mov     rax, [rcx+18h]
0x18002217b  mov     qword ptr [rsp+140h+var_E8], rax
0x180022180  mov     rax, [rcx+20h]
0x180022184  mov     qword ptr [rsp+140h+var_F8+8], rax
0x180022189  mov     eax, [rcx+38h]
0x18002218c  lea     rcx, [rsp+140h+var_F8]
0x180022191  mov     dword ptr [rsp+140h+var_E8+8], eax
0x180022195  call    SyncItemAddServerEnumInfo
0x18002219a  mov     rdx, [rsp+140h+lpAddress]
0x18002219f  lea     rcx, [rsp+140h+var_D0]
0x1800221a4  xor     r9d, r9d
0x1800221a7  xor     r8d, r8d
0x1800221aa  mov     rdx, [rdx+10h]
0x1800221ae  call    SyncItemPatchChangeDescriptors
0x1800221b3  mov     rax, cs:WPP_GLOBAL_Control
0x1800221ba  lea     r13, WPP_GLOBAL_Control
0x1800221c1  cmp     rax, r13
0x1800221c4  jz      short loc_18002222A
0x1800221c6  test    byte ptr [rax+6Ch], 2
0x1800221ca  jz      short loc_18002222A
0x1800221cc  mov     rax, [rsp+140h+lpAddress]
0x1800221d1  lea     rcx, aSynctreeaction_43; "SyncTreeActionCreateAndInitializeContex"...
0x1800221d8  xor     edi, edi
0x1800221da  test    r14d, r14d
0x1800221dd  mov     rdx, [rax+10h]
0x1800221e1  setnz   dil
0x1800221e5  xor     ebx, ebx
0x1800221e7  mov     r9d, edi
0x1800221ea  test    r15d, r15d
0x1800221ed  mov     edx, [rdx]
0x1800221ef  setnz   bl
0x1800221f2  mov     r8d, ebx
0x1800221f5  call    SyncTraceOutputInternal
0x1800221fa  mov     rax, [rsp+140h+lpAddress]
0x1800221ff  lea     r8, WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids
0x180022206  mov     rcx, cs:WPP_GLOBAL_Control
0x18002220d  mov     edx, 13h
0x180022212  mov     dword ptr [rsp+140h+var_118], edi
0x180022216  mov     dword ptr [rsp+140h+var_120], ebx
0x18002221a  mov     r9, [rax+10h]
0x18002221e  mov     rcx, [rcx+60h]
0x180022222  mov     r9d, [r9]
0x180022225  call    WPP_SF_DDD
0x18002222a  mov     rax, [rsp+140h+lpAddress]
0x18002222f  mov     [r12], rax
0x180022233  jmp     short loc_18002229E
0x180022235  mov     rax, cs:WPP_GLOBAL_Control
0x18002223c  cmp     rax, r13
0x18002223f  jz      short loc_18002227B
0x180022241  test    byte ptr [rax+6Ch], 1
0x180022245  jz      short loc_18002227B
0x180022247  mov     edx, esi
0x180022249  lea     rcx, aSynctreeaction_6; "SyncTreeActionNewContext: SyncOpenFileR"...
0x180022250  call    SyncTraceOutputInternal
0x180022255  mov     rcx, cs:WPP_GLOBAL_Control
0x18002225c  lea     r8, WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids
0x180022263  mov     edx, 10h
0x180022268  mov     r9d, esi
0x18002226b  mov     rcx, [rcx+60h]
0x18002226f  call    WPP_SF_d
0x180022274  mov     rax, cs:WPP_GLOBAL_Control
0x18002227b  test    esi, esi
0x18002227d  jz      short loc_1800222A5
0x18002227f  mov     rcx, [rsp+140h+lpAddress]; lpAddress
0x180022284  test    rcx, rcx
0x180022287  jz      short loc_1800222A5
0x180022289  inc     cs:NumLargeFree
0x180022290  xor     edx, edx; dwSize
0x180022292  mov     r8d, 8000h; dwFreeType
0x180022298  call    cs:__imp_VirtualFree
0x18002229e  mov     rax, cs:WPP_GLOBAL_Control
0x1800222a5  cmp     rax, r13
0x1800222a8  jz      short loc_1800222DD
0x1800222aa  test    byte ptr [rax+6Ch], 8
0x1800222ae  jz      short loc_1800222DD
0x1800222b0  mov     edx, esi
0x1800222b2  lea     rcx, aSynctreeaction_41; "SyncTreeActionCreateAndInitializeContex"...
0x1800222b9  call    SyncTraceOutputInternal
0x1800222be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800222c5  lea     r8, WPP_53846ee93eae3a0e9289d7f0d980bfeb_Traceguids
  ... truncated ...
```
