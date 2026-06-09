# VidSchEscape

- ea: `0x1400526e0`
- end: `0x1400529d7`
- name: `VidSchEscape`
- size: `759`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1400045ec`
- `0x140021c90`
- `0x14002a250`
- `0x14002f510`
- `0x1400526e0`
- `0x140055ba8`

## import_xrefs

- `ntoskrnl!RtlSetBitEx` at `0x14005299f`
- `ntoskrnl!RtlSetBitEx` at `0x14005299f`
- `ntoskrnl!RtlIsZeroMemory` at `0x140052742`
- `ntoskrnl!RtlIsZeroMemory` at `0x140052742`
- `ntoskrnl!KeSetEvent` at `0x140052987`
- `ntoskrnl!KeSetEvent` at `0x140052987`
- `watchdog!WdLogSingleEntry1` at `0x14005275a`
- `watchdog!WdLogSingleEntry1` at `0x1400527be`
- `watchdog!WdLogSingleEntry1` at `0x140052837`
- `watchdog!WdLogSingleEntry1` at `0x14005275a`
- `watchdog!WdLogSingleEntry1` at `0x1400527be`
- `watchdog!WdLogSingleEntry1` at `0x140052837`
- `dxgkrnl!g_TdrConfig` at `0x1400528c3`
- `dxgkrnl!g_TdrConfig` at `0x1400528d0`

## pseudocode

```c
__int64 __fastcall VidSchEscape(__int64 a1, __int64 a2)
{
  unsigned int v4; // ebx
  int v5; // ecx
  int v6; // r8d
  __int64 v7; // rcx
  unsigned int v8; // eax
  __int64 v9; // rbp
  int v10; // ecx
  int v11; // r8d
  int v12; // ecx
  unsigned int v13; // eax
  int v14; // eax
  __int64 v15; // rax
  __int64 *v16; // rcx
  __int64 v17; // rdx
  _BYTE v19[88]; // [rsp+50h] [rbp-58h] BYREF

  v4 = -1073741811;
  if ( !*(_DWORD *)a2 )
  {
    v12 = *(_DWORD *)(a2 + 4) != 0;
    v13 = *(_DWORD *)(a1 + 2904) & 0xFFFFFFFE;
    goto LABEL_39;
  }
  if ( *(_DWORD *)a2 != 2 )
  {
    if ( *(_DWORD *)a2 != 4 )
    {
      switch ( *(_DWORD *)a2 )
      {
        case 5:
          g_TdrConfig[6] = *(_DWORD *)(a2 + 4);
          g_TdrConfig[7] = *(_DWORD *)(a2 + 8);
          return 0;
        case 6:
          VidSchiForceTdr(a1);
          return 0;
        case 7:
          *(_DWORD *)(a1 + 256) = *(_DWORD *)(a2 + 4);
          return 0;
        case 8:
          if ( !(unsigned __int8)RtlIsZeroMemory(a2 + 32, 16) )
          {
            WdLogSingleEntry1(1, -1073741811);
            WdLogGlobalForLineNumber = 9568;
            DxgkLogInternalTriageEvent(
              v5,
              0x40000,
              v6,
              (unsigned int)L"Reserved fields should not be set, returning 0x%I64x",
              -1073741811,
              0,
              0,
              0);
            return v4;
          }
          v7 = *(unsigned int *)(a2 + 12);
          v8 = *(_DWORD *)(a2 + 16);
          if ( !(_DWORD)v7 )
          {
            v9 = v8;
            if ( v8 > *(_DWORD *)(a1 + 48) )
            {
              WdLogSingleEntry1(1, v8);
              WdLogGlobalForLineNumber = 9580;
LABEL_14:
              DxgkLogInternalTriageEvent(v10, 0x40000, v11, (unsigned int)L"Invalid VidPnSourceId:%u", v9, 0, 0, 0);
              return v4;
            }
            AcquireSpinLock::AcquireSpinLock((AcquireSpinLock *)v19, (unsigned __int64 *)(a1 + 2096), 1, 0);
            *(_DWORD *)(*(_QWORD *)(a1 + 8 * v9 + 3528) + 83096LL) = *(_DWORD *)(a2 + 28);
            goto LABEL_20;
          }
          if ( (_DWORD)v7 == 1 )
          {
            v9 = *(unsigned int *)(a2 + 16);
            if ( v8 > *(_DWORD *)(a1 + 48) )
            {
              WdLogSingleEntry1(v7, *(unsigned int *)(a2 + 16));
              WdLogGlobalForLineNumber = 9594;
              goto LABEL_14;
            }
            AcquireSpinLock::AcquireSpinLock((AcquireSpinLock *)v19, (unsigned __int64 *)(a1 + 2096), 1, 0);
            *(_DWORD *)(*(_QWORD *)(a1 + 8 * v9 + 3528) + 83092LL) = *(_DWORD *)(a2 + 24);
LABEL_20:
            v4 = 0;
            AcquireSpinLock::Release((AcquireSpinLock *)v19);
            return v4;
          }
          if ( (_DWORD)v7 != 2 )
            return v4;
          *(_BYTE *)(*((_QWORD *)DXGPROCESS::GetCurrent() + 8) + 138LL) = *(_BYTE *)(a2 + 20);
          return 0;
      }
      return v4;
    }
    v12 = *(_DWORD *)(a2 + 4) != 0 ? 0x100 : 0;
    v13 = *(_DWORD *)(a1 + 2904) & 0xFFFFFEFF;
LABEL_39:
    *(_DWORD *)(a1 + 2904) = v13 | v12;
    return 0;
  }
  v14 = *(_DWORD *)(a2 + 4);
  switch ( v14 )
  {
    case 4:
      *(_BYTE *)(a1 + 3364) |= 8u;
      return 0;
    case 5:
      _InterlockedAnd((volatile signed __int32 *)(a1 + 44), 0xFFFFFFF8);
      return 0;
    case 8:
      v15 = *(unsigned int *)(a2 + 8);
      if ( (unsigned int)v15 < *(_DWORD *)(a1 + 88) )
      {
        v16 = *(__int64 **)(a1 + 776);
        if ( (unsigned int)v15 < *(_DWORD *)(a1 + 848) )
          v16 += v15;
        v17 = *v16;
        if ( (*(_DWORD *)(*v16 + 12) & 2) != 0 )
        {
          *(_DWORD *)(v17 + 2156) = 1;
          *(_BYTE *)(v17 + 2154) = 1;
          *(_QWORD *)(a1 + 1576) = MEMORY[0xFFFFF78000000320];
          KeSetEvent((PRKEVENT)(a1 + 1544), 0, 0);
          return v4;
        }
        RtlSetBitEx(a1 + 728, (unsigned int)v15);
        return 0;
      }
      break;
  }
  return v4;
}

```

## disassembly

```asm
0x1400526e0  push    rbx
0x1400526e2  push    rbp
0x1400526e3  push    rsi
0x1400526e4  push    rdi
0x1400526e5  sub     rsp, 88h
0x1400526ec  mov     rdi, rcx
0x1400526ef  mov     rsi, rdx
0x1400526f2  mov     ecx, [rdx]
0x1400526f4  mov     rbx, 0FFFFFFFFC000000Dh
0x1400526fb  test    ecx, ecx
0x1400526fd  jz      loc_1400529AD
0x140052703  sub     ecx, 2
0x140052706  jz      loc_1400528FE
0x14005270c  sub     ecx, 2
0x14005270f  jz      loc_1400528E2
0x140052715  sub     ecx, 1
0x140052718  jz      loc_1400528C3
0x14005271e  sub     ecx, 1
0x140052721  jz      loc_1400528B6
0x140052727  sub     ecx, 1
0x14005272a  jz      loc_1400528A8
0x140052730  cmp     ecx, 1
0x140052733  jnz     loc_1400529C8
0x140052739  lea     rcx, [rdx+20h]
0x14005273d  mov     edx, 10h
0x140052742  call    cs:__imp_RtlIsZeroMemory
0x140052749  nop     dword ptr [rax+rax+00h]
0x14005274e  test    al, al
0x140052750  jnz     short loc_1400527A6
0x140052752  mov     rdx, rbx
0x140052755  mov     ecx, 1
0x14005275a  call    cs:__imp_WdLogSingleEntry1
0x140052761  nop     dword ptr [rax+rax+00h]
0x140052766  mov     [rsp+0A8h+var_70], 0
0x14005276f  lea     r9, aReservedFields; "Reserved fields should not be set, retu"...
0x140052776  mov     [rsp+0A8h+var_78], 0
0x14005277f  mov     [rsp+0A8h+var_80], 0
0x140052788  mov     [rsp+0A8h+var_88], rbx
0x14005278d  mov     cs:WdLogGlobalForLineNumber, 2560h
0x140052797  mov     edx, 40000h
0x14005279c  call    DxgkLogInternalTriageEvent
0x1400527a1  jmp     loc_1400529C8
0x1400527a6  mov     ecx, [rsi+0Ch]
0x1400527a9  mov     eax, [rsi+10h]
0x1400527ac  test    ecx, ecx
0x1400527ae  jnz     short loc_140052827
0x1400527b0  mov     ebp, eax
0x1400527b2  cmp     eax, [rdi+30h]
0x1400527b5  jbe     short loc_1400527FD
0x1400527b7  mov     edx, eax
0x1400527b9  mov     ecx, 1
0x1400527be  call    cs:__imp_WdLogSingleEntry1
0x1400527c5  nop     dword ptr [rax+rax+00h]
0x1400527ca  mov     cs:WdLogGlobalForLineNumber, 256Ch
0x1400527d4  mov     [rsp+0A8h+var_70], 0
0x1400527dd  lea     r9, aInvalidVidpnso_3; "Invalid VidPnSourceId:%u"
0x1400527e4  mov     [rsp+0A8h+var_78], 0
0x1400527ed  mov     [rsp+0A8h+var_80], 0
0x1400527f6  mov     [rsp+0A8h+var_88], rbp
0x1400527fb  jmp     short loc_140052797
0x1400527fd  lea     rdx, [rdi+830h]; unsigned __int64 *
0x140052804  xor     r9d, r9d; bool
0x140052807  mov     r8b, 1; bool
0x14005280a  lea     rcx, [rsp+0A8h+var_58]; this
0x14005280f  call    ??0AcquireSpinLock@@QEAA@AEA_K_N1@Z; AcquireSpinLock::AcquireSpinLock(unsigned __int64 &,bool,bool)
0x140052814  mov     rcx, [rdi+rbp*8+0DC8h]
0x14005281c  mov     eax, [rsi+1Ch]
0x14005281f  mov     [rcx+14498h], eax
0x140052825  jmp     short loc_140052877
0x140052827  cmp     ecx, 1
0x14005282a  jnz     short loc_140052888
0x14005282c  mov     rbp, rax
0x14005282f  cmp     eax, [rdi+30h]
0x140052832  jbe     short loc_14005284F
0x140052834  mov     rdx, rax
0x140052837  call    cs:__imp_WdLogSingleEntry1
0x14005283e  nop     dword ptr [rax+rax+00h]
0x140052843  mov     cs:WdLogGlobalForLineNumber, 257Ah
0x14005284d  jmp     short loc_1400527D4
0x14005284f  lea     rdx, [rdi+830h]; unsigned __int64 *
0x140052856  xor     r9d, r9d; bool
0x140052859  mov     r8b, 1; bool
0x14005285c  lea     rcx, [rsp+0A8h+var_58]; this
0x140052861  call    ??0AcquireSpinLock@@QEAA@AEA_K_N1@Z; AcquireSpinLock::AcquireSpinLock(unsigned __int64 &,bool,bool)
0x140052866  mov     rcx, [rdi+rbp*8+0DC8h]
0x14005286e  mov     eax, [rsi+18h]
0x140052871  mov     [rcx+14494h], eax
0x140052877  xor     ebx, ebx
0x140052879  lea     rcx, [rsp+0A8h+var_58]; this
0x14005287e  call    ?Release@AcquireSpinLock@@QEAAXXZ; AcquireSpinLock::Release(void)
0x140052883  jmp     loc_1400529C8
0x140052888  cmp     ecx, 2
0x14005288b  jnz     loc_1400529C8
0x140052891  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x140052896  mov     rcx, [rax+40h]
0x14005289a  mov     al, [rsi+14h]
0x14005289d  mov     [rcx+8Ah], al
0x1400528a3  jmp     loc_1400529C6
0x1400528a8  mov     eax, [rdx+4]
0x1400528ab  mov     [rdi+100h], eax
0x1400528b1  jmp     loc_1400529C6
0x1400528b6  mov     rcx, rdi
0x1400528b9  call    VidSchiForceTdr
0x1400528be  jmp     loc_1400529C6
0x1400528c3  mov     rax, cs:?g_TdrConfig@@3U_TDR_CONFIG@@C; _TDR_CONFIG volatile g_TdrConfig
0x1400528ca  mov     ecx, [rdx+4]
0x1400528cd  mov     [rax+18h], ecx
0x1400528d0  mov     rax, cs:?g_TdrConfig@@3U_TDR_CONFIG@@C; _TDR_CONFIG volatile g_TdrConfig
0x1400528d7  mov     ecx, [rdx+8]
0x1400528da  mov     [rax+1Ch], ecx
0x1400528dd  jmp     loc_1400529C6
0x1400528e2  mov     eax, [rdx+4]
0x1400528e5  neg     eax
0x1400528e7  mov     eax, [rdi+0B58h]
0x1400528ed  sbb     ecx, ecx
0x1400528ef  and     ecx, 100h
0x1400528f5  btr     eax, 8
0x1400528f9  jmp     loc_1400529BE
0x1400528fe  mov     eax, [rdx+4]
0x140052901  cmp     eax, 4
0x140052904  jnz     short loc_140052912
0x140052906  or      byte ptr [rdi+0D24h], 8
0x14005290d  jmp     loc_1400529C6
0x140052912  cmp     eax, 5
0x140052915  jnz     short loc_140052921
0x140052917  lock and dword ptr [rdi+2Ch], 0FFFFFFF8h
0x14005291c  jmp     loc_1400529C6
0x140052921  cmp     eax, 8
0x140052924  jnz     loc_1400529C8
0x14005292a  mov     eax, [rdx+8]
0x14005292d  cmp     eax, [rdi+58h]
0x140052930  jnb     loc_1400529C8
0x140052936  mov     r8d, eax
0x140052939  mov     rcx, [rdi+308h]
0x140052940  cmp     eax, [rdi+350h]
0x140052946  jnb     short loc_14005294C
0x140052948  lea     rcx, [rcx+rax*8]
0x14005294c  mov     rdx, [rcx]
0x14005294f  mov     eax, [rdx+0Ch]
0x140052952  test    al, 2
0x140052954  jz      short loc_140052995
0x140052956  mov     dword ptr [rdx+86Ch], 1
0x140052960  lea     rcx, [rdi+608h]; Event
0x140052967  mov     byte ptr [rdx+86Ah], 1
0x14005296e  mov     rax, 0FFFFF78000000320h
0x140052978  xor     r8d, r8d; Wait
0x14005297b  xor     edx, edx; Increment
0x14005297d  mov     rax, [rax]
0x140052980  mov     [rdi+628h], rax
0x140052987  call    cs:__imp_KeSetEvent
0x14005298e  nop     dword ptr [rax+rax+00h]
0x140052993  jmp     short loc_1400529C8
0x140052995  lea     rcx, [rdi+2D8h]
0x14005299c  mov     rdx, r8
0x14005299f  call    cs:__imp_RtlSetBitEx
0x1400529a6  nop     dword ptr [rax+rax+00h]
0x1400529ab  jmp     short loc_1400529C6
0x1400529ad  mov     eax, [rdi+0B58h]
0x1400529b3  xor     ecx, ecx
0x1400529b5  cmp     [rdx+4], ecx
0x1400529b8  setnz   cl
0x1400529bb  and     eax, 0FFFFFFFEh
0x1400529be  or      ecx, eax
0x1400529c0  mov     [rdi+0B58h], ecx
0x1400529c6  xor     ebx, ebx
0x1400529c8  mov     eax, ebx
0x1400529ca  add     rsp, 88h
0x1400529d1  pop     rdi
0x1400529d2  pop     rsi
0x1400529d3  pop     rbp
0x1400529d4  pop     rbx
0x1400529d5  retn
```
