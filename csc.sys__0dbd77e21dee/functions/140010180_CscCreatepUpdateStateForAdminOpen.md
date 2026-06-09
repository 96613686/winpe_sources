# CscCreatepUpdateStateForAdminOpen

- ea: `0x140010180`
- end: `0x1400103b8`
- name: `CscCreatepUpdateStateForAdminOpen`
- size: `568`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x140062b70`

## callees

- `0x14000a64c`
- `0x14000f8b0`
- `0x140010040`
- `0x140010180`
- `0x1400169d4`
- `0x140016a04`
- `0x1400190ec`
- `0x14002f010`
- `0x14004fbe0`

## import_xrefs

- `rdbss!RxUpdateNetRootCachingMode` at `0x140010385`
- `rdbss!RxUpdateNetRootCachingMode` at `0x140010385`
- `rdbss!RxQueryNetRootCachingMode` at `0x1400102cc`
- `rdbss!RxQueryNetRootCachingMode` at `0x1400102cc`

## pseudocode

```c
__int64 __fastcall CscCreatepUpdateStateForAdminOpen(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  int InformationEntry; // ebx
  int v6; // r14d
  char v8; // al
  __int64 v9; // rbp
  int Entry; // eax
  __int64 v11; // rdi
  unsigned int v12; // eax
  _QWORD v13[2]; // [rsp+40h] [rbp-98h] BYREF
  _OWORD v14[5]; // [rsp+50h] [rbp-88h] BYREF

  v2 = *(_QWORD *)(a1 + 656);
  memset(v14, 0, sizeof(v14));
  InformationEntry = 0;
  v13[0] = 0;
  v6 = 0;
  if ( (*(_DWORD *)(v2 + 56) & 0x40) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
    v8 = *(_BYTE *)(a2 + 533);
    if ( v8 < 0 )
    {
      *(_BYTE *)(a2 + 533) = v8 | 0x40;
      v9 = *(_QWORD *)(v2 + 32);
      if ( (unsigned int)RxQueryNetRootCachingMode(v9) == -1 )
      {
        Entry = CscStoreFindEntryEx(
                  (unsigned int)v13,
                  0,
                  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 56) + 128LL) + 56LL),
                  0,
                  0);
        v11 = v13[0];
        InformationEntry = Entry;
        if ( Entry >= 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 66, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v13[0]);
          }
          InformationEntry = CscStoreQueryInformationEntryEx(v11, 0, (unsigned int)v14, 0, 0, 0, 0);
          if ( InformationEntry >= 0 )
          {
            v12 = CscConvertStoreCacheModeToSmbCacheMode(SDWORD2(v14[0]));
            RxUpdateNetRootCachingMode(v9, v12);
          }
          else
          {
            v6 = 4414;
          }
        }
        else
        {
          v6 = 4405;
        }
        if ( v11 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 67, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v11);
          }
          CscEnDereferenceEntry(v13);
        }
      }
    }
    else
    {
      InformationEntry = -1073740768;
      v6 = 4381;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      68,
      WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
      (unsigned int)InformationEntry,
      v6);
  return (unsigned int)InformationEntry;
}

```

## disassembly

```asm
0x140010180  mov     r11, rsp
0x140010183  mov     [r11+18h], rbx
0x140010187  mov     [r11+20h], rbp
0x14001018b  push    rsi
0x14001018c  push    rdi
0x14001018d  push    r12
0x14001018f  push    r14
0x140010191  push    r15
0x140010193  sub     rsp, 0B0h
0x14001019a  mov     rax, cs:__security_cookie
0x1400101a1  xor     rax, rsp
0x1400101a4  mov     [rsp+0D8h+var_38], rax
0x1400101ac  mov     rdi, [rcx+290h]
0x1400101b3  lea     r12, WPP_GLOBAL_Control
0x1400101ba  xorps   xmm0, xmm0
0x1400101bd  xor     r15d, r15d
0x1400101c0  movups  [rsp+0D8h+var_88], xmm0
0x1400101c5  mov     rbp, rdx
0x1400101c8  mov     rsi, rcx
0x1400101cb  movups  [rsp+0D8h+var_78], xmm0
0x1400101d0  mov     ebx, r15d
0x1400101d3  mov     [rsp+0D8h+var_98], r15
0x1400101d8  movups  [rsp+0D8h+var_68], xmm0
0x1400101dd  mov     r14d, r15d
0x1400101e0  movups  xmmword ptr [r11-58h], xmm0
0x1400101e5  movups  xmmword ptr [r11-48h], xmm0
0x1400101ea  mov     eax, [rdi+38h]
0x1400101ed  test    al, 40h
0x1400101ef  jnz     loc_14001027A
0x1400101f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400101fc  cmp     rcx, r12
0x1400101ff  jz      short loc_14001020C
0x140010201  mov     eax, [rcx+2Ch]
0x140010204  test    al, 40h
0x140010206  jnz     loc_140010396
0x14001020c  mov     eax, ebx
0x14001020e  mov     rcx, [rsp+0D8h+var_38]
0x140010216  xor     rcx, rsp; StackCookie
0x140010219  call    __security_check_cookie
0x14001021e  lea     r11, [rsp+0D8h+var_28]
0x140010226  mov     rbx, [r11+40h]
0x14001022a  mov     rbp, [r11+48h]
0x14001022e  mov     rsp, r11
0x140010231  pop     r15
0x140010233  pop     r14
0x140010235  pop     r12
0x140010237  pop     rdi
0x140010238  pop     rsi
0x140010239  retn
0x14001023b  test    rdi, rdi
0x14001023e  jz      short loc_1400101F5
0x140010240  mov     rcx, cs:WPP_GLOBAL_Control
0x140010247  cmp     rcx, r12
0x14001024a  jz      short loc_14001026B
0x14001024c  mov     eax, [rcx+2Ch]
0x14001024f  test    al, 40h
0x140010251  jz      short loc_14001026B
0x140010253  mov     rcx, [rcx+18h]
0x140010257  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x14001025e  mov     edx, 43h ; 'C'
0x140010263  mov     r9, rdi
0x140010266  call    WPP_SF_q
0x14001026b  lea     rcx, [rsp+0D8h+var_98]
0x140010270  call    CscEnDereferenceEntry
0x140010275  jmp     loc_1400101F5
0x14001027a  mov     rcx, cs:WPP_GLOBAL_Control
0x140010281  cmp     rcx, r12
0x140010284  jz      short loc_1400102A2
0x140010286  mov     eax, [rcx+2Ch]
0x140010289  test    al, 40h
0x14001028b  jz      short loc_1400102A2
0x14001028d  mov     rcx, [rcx+18h]
0x140010291  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x140010298  mov     edx, 41h ; 'A'
0x14001029d  call    WPP_SF_
0x1400102a2  movzx   eax, byte ptr [rbp+215h]
0x1400102a9  test    al, al
0x1400102ab  js      short loc_1400102BD
0x1400102ad  mov     ebx, 0C0000420h
0x1400102b2  mov     r14d, 111Dh
0x1400102b8  jmp     loc_1400101F5
0x1400102bd  or      al, 40h
0x1400102bf  mov     [rbp+215h], al
0x1400102c5  mov     rbp, [rdi+20h]
0x1400102c9  mov     rcx, rbp
0x1400102cc  call    cs:__imp_RxQueryNetRootCachingMode
0x1400102d3  nop     dword ptr [rax+rax+00h]
0x1400102d8  cmp     eax, 0FFFFFFFFh
0x1400102db  jnz     loc_1400101F5
0x1400102e1  mov     rax, [rsi+38h]
0x1400102e5  lea     rcx, [rsp+0D8h+var_98]
0x1400102ea  xor     r9d, r9d
0x1400102ed  mov     [rsp+0D8h+var_B8], r15
0x1400102f2  xor     edx, edx
0x1400102f4  mov     r8, [rax+80h]
0x1400102fb  mov     r8, [r8+38h]
0x1400102ff  call    CscStoreFindEntryEx
0x140010304  mov     rdi, [rsp+0D8h+var_98]
0x140010309  mov     ebx, eax
0x14001030b  test    eax, eax
0x14001030d  jns     short loc_14001031A
0x14001030f  mov     r14d, 1135h
0x140010315  jmp     loc_14001023B
0x14001031a  mov     rcx, cs:WPP_GLOBAL_Control
0x140010321  cmp     rcx, r12
0x140010324  jz      short loc_140010345
0x140010326  mov     eax, [rcx+2Ch]
0x140010329  test    al, 40h
0x14001032b  jz      short loc_140010345
0x14001032d  mov     rcx, [rcx+18h]
0x140010331  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x140010338  mov     edx, 42h ; 'B'
0x14001033d  mov     r9, rdi
0x140010340  call    WPP_SF_q
0x140010345  mov     [rsp+0D8h+var_A8], r15
0x14001034a  lea     r8, [rsp+0D8h+var_88]
0x14001034f  mov     [rsp+0D8h+var_B0], r15
0x140010354  xor     r9d, r9d
0x140010357  xor     edx, edx
0x140010359  mov     [rsp+0D8h+var_B8], r15
0x14001035e  mov     rcx, rdi
0x140010361  call    CscStoreQueryInformationEntryEx
0x140010366  mov     ebx, eax
0x140010368  test    eax, eax
0x14001036a  jns     short loc_140010377
0x14001036c  mov     r14d, 113Eh
0x140010372  jmp     loc_14001023B
0x140010377  mov     ecx, dword ptr [rsp+0D8h+var_88+8]
0x14001037b  call    CscConvertStoreCacheModeToSmbCacheMode
0x140010380  mov     edx, eax
0x140010382  mov     rcx, rbp
0x140010385  call    cs:__imp_RxUpdateNetRootCachingMode
0x14001038c  nop     dword ptr [rax+rax+00h]
0x140010391  jmp     loc_14001023B
0x140010396  mov     rcx, [rcx+18h]
0x14001039a  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x1400103a1  mov     edx, 44h ; 'D'
0x1400103a6  mov     dword ptr [rsp+0D8h+var_B8], r14d
0x1400103ab  mov     r9d, ebx
0x1400103ae  call    WPP_SF_Dd
0x1400103b3  jmp     loc_14001020C
```
