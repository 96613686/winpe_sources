# PortMgrDeInitPortHelper

- ea: `0x18001be88`
- end: `0x18001c11b`
- name: `PortMgrDeInitPortHelper`
- size: `659`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180023640`
- `0x1800238b8`

## callees

- `0x180005440`
- `0x18000ad00`
- `0x18000c4c0`
- `0x18000c5a0`
- `0x180010d40`
- `0x18001be88`
- `0x1800214f0`
- `0x180022104`

## import_xrefs

- `MobileNetworking!DeleteTimer` at `0x18001bef9`
- `MobileNetworking!DeleteTimer` at `0x18001bef9`
- `MobileNetworking!FreeMemory` at `0x18001c07f`
- `MobileNetworking!FreeMemory` at `0x18001c0bb`
- `MobileNetworking!FreeMemory` at `0x18001c07f`
- `MobileNetworking!FreeMemory` at `0x18001c0bb`
- `MobileNetworking!DeleteReadWriteLock` at `0x18001c044`
- `MobileNetworking!DeleteReadWriteLock` at `0x18001c044`

## pseudocode

```c
void __fastcall PortMgrDeInitPortHelper(__int64 a1, int a2, int a3, int a4)
{
  _QWORD *v8; // r10
  int v9; // ebp
  _QWORD *v10; // rdi
  _QWORD *v11; // rax
  __int64 v12; // rcx
  _QWORD *v13; // rsi
  __int64 GlobalEventDescription; // rax
  __int64 v15; // r10
  _BYTE *v16; // rax
  __int64 v17; // rdx
  _BYTE *v18; // rax
  __int64 v19; // r8

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    if ( a3 )
    {
      DeleteTimer(*(_QWORD *)(a1 + 2888));
      *(_QWORD *)(a1 + 2888) = 0;
      v8 = WPP_GLOBAL_Control;
    }
    if ( a2 )
    {
      v9 = *(_DWORD *)(a1 + 20);
      v10 = (_QWORD *)(a1 + 176);
      if ( v8 != &WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)v8 + 17) & 0x800) != 0 )
        {
          WPP_SF_(v8[7], 46, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
          v8 = WPP_GLOBAL_Control;
        }
        if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 68) & 0x40) != 0 )
        {
          WPP_SF_dS(
            v8[7],
            47,
            (unsigned int)WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids,
            v9,
            (__int64)L"GlobalQueue");
          v8 = WPP_GLOBAL_Control;
        }
      }
      while ( 1 )
      {
        v11 = (_QWORD *)*v10;
        if ( (_QWORD *)*v10 == v10 )
          break;
        if ( (_QWORD *)v11[1] != v10 || (v12 = *v11, *(_QWORD **)(*v11 + 8LL) != v11) )
          __fastfail(3u);
        *v10 = v12;
        v13 = v11;
        *(_QWORD *)(v12 + 8) = v10;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x40) != 0 )
        {
          GlobalEventDescription = GetGlobalEventDescription(*((unsigned int *)v11 + 4));
          WPP_SF_dSS(
            *(_QWORD *)(v15 + 56),
            48,
            (unsigned int)WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids,
            v9,
            GlobalEventDescription,
            (__int64)L"GlobalQueue");
        }
        OneXDeleteEvent(v13);
        v8 = WPP_GLOBAL_Control;
      }
      if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 17) & 0x800) != 0 )
      {
        WPP_SF_D(v8[7], 50, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, 0);
        v8 = WPP_GLOBAL_Control;
      }
    }
    if ( a4 )
    {
      DeleteReadWriteLock(a1 + 2896);
      v8 = WPP_GLOBAL_Control;
    }
    v16 = *(_BYTE **)(a1 + 56);
    if ( v16 && *(_DWORD *)(a1 + 48) )
    {
      v17 = *(unsigned int *)(a1 + 48);
      do
      {
        *v16++ = 0;
        --v17;
      }
      while ( v17 );
      FreeMemory(a1 + 56, "PortMgrDeInitPortHelper", 165);
      v8 = WPP_GLOBAL_Control;
    }
    v18 = *(_BYTE **)(a1 + 72);
    if ( v18 && *(_DWORD *)(a1 + 64) )
    {
      v19 = *(unsigned int *)(a1 + 64);
      do
      {
        *v18++ = 0;
        --v19;
      }
      while ( v19 );
      FreeMemory(a1 + 72, "PortMgrDeInitPortHelper", 171);
      v8 = WPP_GLOBAL_Control;
    }
    if ( *(_QWORD *)(a1 + 104) )
    {
      FreeEapError();
      v8 = WPP_GLOBAL_Control;
    }
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 17) & 0x800) != 0 )
    WPP_SF_D(v8[7], 22, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, 0);
}

```

## disassembly

```asm
0x18001be88  mov     [rsp+arg_8], rbx
0x18001be8d  mov     [rsp+arg_10], rbp
0x18001be92  push    rsi
0x18001be93  push    rdi
0x18001be94  push    r12
0x18001be96  push    r14
0x18001be98  push    r15
0x18001be9a  sub     rsp, 30h
0x18001be9e  mov     r14d, r9d
0x18001bea1  mov     edi, r8d
0x18001bea4  mov     esi, edx
0x18001bea6  mov     rbx, rcx
0x18001bea9  mov     r10, cs:WPP_GLOBAL_Control
0x18001beb0  lea     r12, WPP_GLOBAL_Control
0x18001beb7  cmp     r10, r12
0x18001beba  jz      short loc_18001BEE2
0x18001bebc  test    dword ptr [r10+44h], 800h
0x18001bec4  jz      short loc_18001BEE2
0x18001bec6  mov     rcx, [r10+38h]
0x18001beca  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18001bed1  mov     edx, 15h
0x18001bed6  call    WPP_SF_
0x18001bedb  mov     r10, cs:WPP_GLOBAL_Control
0x18001bee2  xor     r15d, r15d
0x18001bee5  test    rbx, rbx
0x18001bee8  jz      loc_18001C0DD
0x18001beee  test    edi, edi
0x18001bef0  jz      short loc_18001BF0D
0x18001bef2  mov     rcx, [rbx+0B48h]
0x18001bef9  call    cs:__imp_DeleteTimer
0x18001beff  mov     [rbx+0B48h], r15
0x18001bf06  mov     r10, cs:WPP_GLOBAL_Control
0x18001bf0d  test    esi, esi
0x18001bf0f  jz      loc_18001C038
0x18001bf15  mov     ebp, [rbx+14h]
0x18001bf18  lea     rdi, [rbx+0B0h]
0x18001bf1f  lea     rax, aGlobalqueue; "GlobalQueue"
0x18001bf26  cmp     r10, r12
0x18001bf29  jz      short loc_18001BF88
0x18001bf2b  test    dword ptr [r10+44h], 800h
0x18001bf33  jz      short loc_18001BF58
0x18001bf35  mov     rcx, [r10+38h]
0x18001bf39  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18001bf40  mov     edx, 2Eh ; '.'
0x18001bf45  call    WPP_SF_
0x18001bf4a  mov     r10, cs:WPP_GLOBAL_Control
0x18001bf51  lea     rax, aGlobalqueue; "GlobalQueue"
0x18001bf58  cmp     r10, r12
0x18001bf5b  jz      short loc_18001BF88
0x18001bf5d  test    byte ptr [r10+44h], 40h
0x18001bf62  jz      short loc_18001BF88
0x18001bf64  mov     rcx, [r10+38h]
0x18001bf68  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18001bf6f  mov     edx, 2Fh ; '/'
0x18001bf74  mov     [rsp+58h+var_38], rax
0x18001bf79  mov     r9d, ebp
0x18001bf7c  call    WPP_SF_dS
0x18001bf81  mov     r10, cs:WPP_GLOBAL_Control
0x18001bf88  lea     r15, aGlobalqueue; "GlobalQueue"
0x18001bf8f  mov     rax, [rdi]
0x18001bf92  cmp     rax, rdi
0x18001bf95  jz      short loc_18001C005
0x18001bf97  cmp     [rax+8], rdi
0x18001bf9b  jnz     short loc_18001BFFE
0x18001bf9d  mov     rcx, [rax]
0x18001bfa0  cmp     [rcx+8], rax
0x18001bfa4  jnz     short loc_18001BFFE
0x18001bfa6  mov     [rdi], rcx
0x18001bfa9  mov     rsi, rax
0x18001bfac  mov     [rcx+8], rdi
0x18001bfb0  mov     r10, cs:WPP_GLOBAL_Control
0x18001bfb7  cmp     r10, r12
0x18001bfba  jz      short loc_18001BFED
0x18001bfbc  test    byte ptr [r10+44h], 40h
0x18001bfc1  jz      short loc_18001BFED
0x18001bfc3  mov     ecx, [rax+10h]
0x18001bfc6  call    GetGlobalEventDescription
0x18001bfcb  mov     rcx, [r10+38h]
0x18001bfcf  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18001bfd6  mov     edx, 30h ; '0'
0x18001bfdb  mov     [rsp+58h+var_30], r15
0x18001bfe0  mov     r9d, ebp
0x18001bfe3  mov     [rsp+58h+var_38], rax
0x18001bfe8  call    WPP_SF_dSS
0x18001bfed  mov     rcx, rsi
0x18001bff0  call    OneXDeleteEvent
0x18001bff5  mov     r10, cs:WPP_GLOBAL_Control
0x18001bffc  jmp     short loc_18001BF8F
0x18001bffe  mov     ecx, 3
0x18001c003  int     29h; Win8: RtlFailFast(ecx)
0x18001c005  mov     r15d, 0
0x18001c00b  cmp     r10, r12
0x18001c00e  jz      short loc_18001C038
0x18001c010  test    dword ptr [r10+44h], 800h
0x18001c018  jz      short loc_18001C038
0x18001c01a  mov     rcx, [r10+38h]
0x18001c01e  lea     edx, [r15+32h]
0x18001c022  xor     r9d, r9d
0x18001c025  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18001c02c  call    WPP_SF_D
0x18001c031  mov     r10, cs:WPP_GLOBAL_Control
0x18001c038  test    r14d, r14d
0x18001c03b  jz      short loc_18001C051
0x18001c03d  lea     rcx, [rbx+0B50h]
0x18001c044  call    cs:__imp_DeleteReadWriteLock
0x18001c04a  mov     r10, cs:WPP_GLOBAL_Control
0x18001c051  lea     rcx, [rbx+38h]
0x18001c055  mov     rax, [rcx]
0x18001c058  test    rax, rax
0x18001c05b  jz      short loc_18001C08C
0x18001c05d  cmp     [rbx+30h], r15d
0x18001c061  jz      short loc_18001C08C
0x18001c063  mov     edx, [rbx+30h]
0x18001c066  mov     [rax], r15b
0x18001c069  inc     rax
0x18001c06c  sub     rdx, 1
0x18001c070  jnz     short loc_18001C066
0x18001c072  mov     r8d, 0A5h
0x18001c078  lea     rdx, aPortmgrdeinitp; "PortMgrDeInitPortHelper"
0x18001c07f  call    cs:__imp_FreeMemory
0x18001c085  mov     r10, cs:WPP_GLOBAL_Control
0x18001c08c  lea     rcx, [rbx+48h]
0x18001c090  mov     rax, [rcx]
0x18001c093  test    rax, rax
0x18001c096  jz      short loc_18001C0C8
0x18001c098  cmp     [rbx+40h], r15d
0x18001c09c  jz      short loc_18001C0C8
0x18001c09e  mov     r8d, [rbx+40h]
0x18001c0a2  mov     [rax], r15b
0x18001c0a5  inc     rax
0x18001c0a8  sub     r8, 1
0x18001c0ac  jnz     short loc_18001C0A2
0x18001c0ae  mov     r8d, 0ABh
0x18001c0b4  lea     rdx, aPortmgrdeinitp; "PortMgrDeInitPortHelper"
0x18001c0bb  call    cs:__imp_FreeMemory
0x18001c0c1  mov     r10, cs:WPP_GLOBAL_Control
0x18001c0c8  mov     rcx, [rbx+68h]
0x18001c0cc  test    rcx, rcx
0x18001c0cf  jz      short loc_18001C0DD
0x18001c0d1  call    FreeEapError
0x18001c0d6  mov     r10, cs:WPP_GLOBAL_Control
0x18001c0dd  cmp     r10, r12
0x18001c0e0  jz      short loc_18001C104
0x18001c0e2  test    dword ptr [r10+44h], 800h
0x18001c0ea  jz      short loc_18001C104
0x18001c0ec  mov     rcx, [r10+38h]
0x18001c0f0  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18001c0f7  mov     edx, 16h
0x18001c0fc  xor     r9d, r9d
0x18001c0ff  call    WPP_SF_D
0x18001c104  mov     rbx, [rsp+58h+arg_8]
0x18001c109  mov     rbp, [rsp+58h+arg_10]
0x18001c10e  add     rsp, 30h
0x18001c112  pop     r15
0x18001c114  pop     r14
0x18001c116  pop     r12
0x18001c118  pop     rdi
0x18001c119  pop     rsi
0x18001c11a  retn
```
