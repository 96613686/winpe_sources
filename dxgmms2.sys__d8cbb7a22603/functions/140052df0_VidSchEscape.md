# VidSchEscape

- ea: `0x140052df0`
- end: `0x1400530e7`
- name: `VidSchEscape`
- size: `759`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x140004268`
- `0x14001f640`
- `0x140027b90`
- `0x14002c5d0`
- `0x140052df0`
- `0x140056478`

## import_xrefs

- `ntoskrnl!RtlSetBitEx` at `0x1400530af`
- `ntoskrnl!RtlSetBitEx` at `0x1400530af`
- `ntoskrnl!RtlIsZeroMemory` at `0x140052e52`
- `ntoskrnl!RtlIsZeroMemory` at `0x140052e52`
- `ntoskrnl!KeSetEvent` at `0x140053097`
- `ntoskrnl!KeSetEvent` at `0x140053097`
- `watchdog!WdLogSingleEntry1` at `0x140052e6a`
- `watchdog!WdLogSingleEntry1` at `0x140052ece`
- `watchdog!WdLogSingleEntry1` at `0x140052f47`
- `watchdog!WdLogSingleEntry1` at `0x140052e6a`
- `watchdog!WdLogSingleEntry1` at `0x140052ece`
- `watchdog!WdLogSingleEntry1` at `0x140052f47`
- `dxgkrnl!g_TdrConfig` at `0x140052fd3`
- `dxgkrnl!g_TdrConfig` at `0x140052fe0`

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
0x140052df0  push    rbx
0x140052df2  push    rbp
0x140052df3  push    rsi
0x140052df4  push    rdi
0x140052df5  sub     rsp, 88h
0x140052dfc  mov     rdi, rcx
0x140052dff  mov     rsi, rdx
0x140052e02  mov     ecx, [rdx]
0x140052e04  mov     rbx, 0FFFFFFFFC000000Dh
0x140052e0b  test    ecx, ecx
0x140052e0d  jz      loc_1400530BD
0x140052e13  sub     ecx, 2
0x140052e16  jz      loc_14005300E
0x140052e1c  sub     ecx, 2
0x140052e1f  jz      loc_140052FF2
0x140052e25  sub     ecx, 1
0x140052e28  jz      loc_140052FD3
0x140052e2e  sub     ecx, 1
0x140052e31  jz      loc_140052FC6
0x140052e37  sub     ecx, 1
0x140052e3a  jz      loc_140052FB8
0x140052e40  cmp     ecx, 1
0x140052e43  jnz     loc_1400530D8
0x140052e49  lea     rcx, [rdx+20h]
0x140052e4d  mov     edx, 10h
0x140052e52  call    cs:__imp_RtlIsZeroMemory
0x140052e59  nop     dword ptr [rax+rax+00h]
0x140052e5e  test    al, al
0x140052e60  jnz     short loc_140052EB6
0x140052e62  mov     rdx, rbx
0x140052e65  mov     ecx, 1
0x140052e6a  call    cs:__imp_WdLogSingleEntry1
0x140052e71  nop     dword ptr [rax+rax+00h]
0x140052e76  mov     [rsp+0A8h+var_70], 0
0x140052e7f  lea     r9, aReservedFields; "Reserved fields should not be set, retu"...
0x140052e86  mov     [rsp+0A8h+var_78], 0
0x140052e8f  mov     [rsp+0A8h+var_80], 0
0x140052e98  mov     [rsp+0A8h+var_88], rbx
0x140052e9d  mov     cs:WdLogGlobalForLineNumber, 2560h
0x140052ea7  mov     edx, 40000h
0x140052eac  call    DxgkLogInternalTriageEvent
0x140052eb1  jmp     loc_1400530D8
0x140052eb6  mov     ecx, [rsi+0Ch]
0x140052eb9  mov     eax, [rsi+10h]
0x140052ebc  test    ecx, ecx
0x140052ebe  jnz     short loc_140052F37
0x140052ec0  mov     ebp, eax
0x140052ec2  cmp     eax, [rdi+30h]
0x140052ec5  jbe     short loc_140052F0D
0x140052ec7  mov     edx, eax
0x140052ec9  mov     ecx, 1
0x140052ece  call    cs:__imp_WdLogSingleEntry1
0x140052ed5  nop     dword ptr [rax+rax+00h]
0x140052eda  mov     cs:WdLogGlobalForLineNumber, 256Ch
0x140052ee4  mov     [rsp+0A8h+var_70], 0
0x140052eed  lea     r9, aInvalidVidpnso_3; "Invalid VidPnSourceId:%u"
0x140052ef4  mov     [rsp+0A8h+var_78], 0
0x140052efd  mov     [rsp+0A8h+var_80], 0
0x140052f06  mov     [rsp+0A8h+var_88], rbp
0x140052f0b  jmp     short loc_140052EA7
0x140052f0d  lea     rdx, [rdi+830h]; unsigned __int64 *
0x140052f14  xor     r9d, r9d; bool
0x140052f17  mov     r8b, 1; bool
0x140052f1a  lea     rcx, [rsp+0A8h+var_58]; this
0x140052f1f  call    ??0AcquireSpinLock@@QEAA@AEA_K_N1@Z; AcquireSpinLock::AcquireSpinLock(unsigned __int64 &,bool,bool)
0x140052f24  mov     rcx, [rdi+rbp*8+0DC8h]
0x140052f2c  mov     eax, [rsi+1Ch]
0x140052f2f  mov     [rcx+14498h], eax
0x140052f35  jmp     short loc_140052F87
0x140052f37  cmp     ecx, 1
0x140052f3a  jnz     short loc_140052F98
0x140052f3c  mov     rbp, rax
0x140052f3f  cmp     eax, [rdi+30h]
0x140052f42  jbe     short loc_140052F5F
0x140052f44  mov     rdx, rax
0x140052f47  call    cs:__imp_WdLogSingleEntry1
0x140052f4e  nop     dword ptr [rax+rax+00h]
0x140052f53  mov     cs:WdLogGlobalForLineNumber, 257Ah
0x140052f5d  jmp     short loc_140052EE4
0x140052f5f  lea     rdx, [rdi+830h]; unsigned __int64 *
0x140052f66  xor     r9d, r9d; bool
0x140052f69  mov     r8b, 1; bool
0x140052f6c  lea     rcx, [rsp+0A8h+var_58]; this
0x140052f71  call    ??0AcquireSpinLock@@QEAA@AEA_K_N1@Z; AcquireSpinLock::AcquireSpinLock(unsigned __int64 &,bool,bool)
0x140052f76  mov     rcx, [rdi+rbp*8+0DC8h]
0x140052f7e  mov     eax, [rsi+18h]
0x140052f81  mov     [rcx+14494h], eax
0x140052f87  xor     ebx, ebx
0x140052f89  lea     rcx, [rsp+0A8h+var_58]; this
0x140052f8e  call    ?Release@AcquireSpinLock@@QEAAXXZ; AcquireSpinLock::Release(void)
0x140052f93  jmp     loc_1400530D8
0x140052f98  cmp     ecx, 2
0x140052f9b  jnz     loc_1400530D8
0x140052fa1  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x140052fa6  mov     rcx, [rax+40h]
0x140052faa  mov     al, [rsi+14h]
0x140052fad  mov     [rcx+8Ah], al
0x140052fb3  jmp     loc_1400530D6
0x140052fb8  mov     eax, [rdx+4]
0x140052fbb  mov     [rdi+100h], eax
0x140052fc1  jmp     loc_1400530D6
0x140052fc6  mov     rcx, rdi
0x140052fc9  call    VidSchiForceTdr
0x140052fce  jmp     loc_1400530D6
0x140052fd3  mov     rax, cs:?g_TdrConfig@@3U_TDR_CONFIG@@C; _TDR_CONFIG volatile g_TdrConfig
0x140052fda  mov     ecx, [rdx+4]
0x140052fdd  mov     [rax+18h], ecx
0x140052fe0  mov     rax, cs:?g_TdrConfig@@3U_TDR_CONFIG@@C; _TDR_CONFIG volatile g_TdrConfig
0x140052fe7  mov     ecx, [rdx+8]
0x140052fea  mov     [rax+1Ch], ecx
0x140052fed  jmp     loc_1400530D6
0x140052ff2  mov     eax, [rdx+4]
0x140052ff5  neg     eax
0x140052ff7  mov     eax, [rdi+0B58h]
0x140052ffd  sbb     ecx, ecx
0x140052fff  and     ecx, 100h
0x140053005  btr     eax, 8
0x140053009  jmp     loc_1400530CE
0x14005300e  mov     eax, [rdx+4]
0x140053011  cmp     eax, 4
0x140053014  jnz     short loc_140053022
0x140053016  or      byte ptr [rdi+0D24h], 8
0x14005301d  jmp     loc_1400530D6
0x140053022  cmp     eax, 5
0x140053025  jnz     short loc_140053031
0x140053027  lock and dword ptr [rdi+2Ch], 0FFFFFFF8h
0x14005302c  jmp     loc_1400530D6
0x140053031  cmp     eax, 8
0x140053034  jnz     loc_1400530D8
0x14005303a  mov     eax, [rdx+8]
0x14005303d  cmp     eax, [rdi+58h]
0x140053040  jnb     loc_1400530D8
0x140053046  mov     r8d, eax
0x140053049  mov     rcx, [rdi+308h]
0x140053050  cmp     eax, [rdi+350h]
0x140053056  jnb     short loc_14005305C
0x140053058  lea     rcx, [rcx+rax*8]
0x14005305c  mov     rdx, [rcx]
0x14005305f  mov     eax, [rdx+0Ch]
0x140053062  test    al, 2
0x140053064  jz      short loc_1400530A5
0x140053066  mov     dword ptr [rdx+86Ch], 1
0x140053070  lea     rcx, [rdi+608h]; Event
0x140053077  mov     byte ptr [rdx+86Ah], 1
0x14005307e  mov     rax, 0FFFFF78000000320h
0x140053088  xor     r8d, r8d; Wait
0x14005308b  xor     edx, edx; Increment
0x14005308d  mov     rax, [rax]
0x140053090  mov     [rdi+628h], rax
0x140053097  call    cs:__imp_KeSetEvent
0x14005309e  nop     dword ptr [rax+rax+00h]
0x1400530a3  jmp     short loc_1400530D8
0x1400530a5  lea     rcx, [rdi+2D8h]
0x1400530ac  mov     rdx, r8
0x1400530af  call    cs:__imp_RtlSetBitEx
0x1400530b6  nop     dword ptr [rax+rax+00h]
0x1400530bb  jmp     short loc_1400530D6
0x1400530bd  mov     eax, [rdi+0B58h]
0x1400530c3  xor     ecx, ecx
0x1400530c5  cmp     [rdx+4], ecx
0x1400530c8  setnz   cl
0x1400530cb  and     eax, 0FFFFFFFEh
0x1400530ce  or      ecx, eax
0x1400530d0  mov     [rdi+0B58h], ecx
0x1400530d6  xor     ebx, ebx
0x1400530d8  mov     eax, ebx
0x1400530da  add     rsp, 88h
0x1400530e1  pop     rdi
0x1400530e2  pop     rsi
0x1400530e3  pop     rbp
0x1400530e4  pop     rbx
0x1400530e5  retn
```
