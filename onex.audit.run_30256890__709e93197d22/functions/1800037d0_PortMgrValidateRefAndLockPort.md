# PortMgrValidateRefAndLockPort

- ea: `0x1800037d0`
- end: `0x180003a13`
- name: `PortMgrValidateRefAndLockPort`
- size: `579`
- prototype: ``
- caller_count: `11`
- callee_count: `5`
- tags: ``

## callers

- `0x180004780`
- `0x180013a30`
- `0x180014e50`
- `0x1800170c0`
- `0x180023d80`
- `0x18002c010`
- `0x18002c1f0`
- `0x18002c8d0`
- `0x18002cae0`
- `0x18002cd10`
- `0x18002d020`

## callees

- `0x1800037d0`
- `0x180005440`
- `0x180010ae0`
- `0x18001d838`
- `0x1800214f0`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x1800038e1`
- `MobileNetworking!ReleaseWriteLock` at `0x180003904`
- `MobileNetworking!ReleaseWriteLock` at `0x1800038e1`
- `MobileNetworking!ReleaseWriteLock` at `0x180003904`
- `MobileNetworking!AcquireWriteLock` at `0x18000389f`
- `MobileNetworking!AcquireWriteLock` at `0x180003997`
- `MobileNetworking!AcquireWriteLock` at `0x18000389f`
- `MobileNetworking!AcquireWriteLock` at `0x180003997`

## pseudocode

```c
__int64 __fastcall PortMgrValidateRefAndLockPort(__int64 a1, __int64 a2, _DWORD *a3, _DWORD *a4)
{
  _QWORD *v7; // rcx
  unsigned int v8; // edi
  __int64 i; // rax
  bool v10; // sf

  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 57, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  v8 = 0;
  *a3 = 0;
  *a4 = 0;
  if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 17) & 0x800) != 0 )
  {
    WPP_SF_(v7[7], 54, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    AcquireWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrValidateAndRefPort", 633);
    for ( i = qword_18003DD68; (__int64 *)i != &qword_18003DD68; i = *(_QWORD *)i )
    {
      if ( a1 == i )
      {
        _InterlockedIncrement((volatile signed __int32 *)(i + 16));
        ReleaseWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrValidateAndRefPort", 650);
        goto LABEL_17;
      }
    }
    ReleaseWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrValidateAndRefPort", 650);
    v8 = 6;
    goto LABEL_17;
  }
  v8 = 6;
  if ( v7 == &WPP_GLOBAL_Control )
    goto LABEL_21;
  if ( (*((_BYTE *)v7 + 68) & 1) != 0 )
  {
    WPP_SF_(v7[7], 55, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids);
LABEL_17:
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 17) & 0x800) != 0 )
  {
    WPP_SF_D(v7[7], 56, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, v8);
    v7 = WPP_GLOBAL_Control;
  }
LABEL_21:
  if ( !v8 )
  {
    *a3 = 1;
    AcquireWriteLock(a1, a1 + 2896, "PortMgrValidateRefAndLockPort", 676);
    v10 = *(int *)(a1 + 24) < 0;
    *a4 = 1;
    if ( v10 )
    {
      v8 = 6;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v8;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_30;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        59,
        WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids,
        *(unsigned int *)(a1 + 20));
    }
    goto LABEL_29;
  }
  if ( v7 == &WPP_GLOBAL_Control )
    return v8;
  if ( (*((_BYTE *)v7 + 68) & 1) != 0 )
  {
    WPP_SF_dq(v7[7], 58, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, v8, a1);
LABEL_29:
    v7 = WPP_GLOBAL_Control;
  }
LABEL_30:
  if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 17) & 0x800) != 0 )
    WPP_SF_D(v7[7], 60, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x1800037d0  push    rbx
0x1800037d2  push    rbp
0x1800037d3  push    rsi
0x1800037d4  push    rdi
0x1800037d5  push    r14
0x1800037d7  sub     rsp, 30h
0x1800037db  mov     rsi, r9
0x1800037de  mov     r14, r8
0x1800037e1  mov     rbx, rcx
0x1800037e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800037eb  lea     rbp, WPP_GLOBAL_Control
0x1800037f2  cmp     rcx, rbp
0x1800037f5  jz      short loc_18000381C
0x1800037f7  test    dword ptr [rcx+44h], 800h
0x1800037fe  jz      short loc_18000381C
0x180003800  mov     rcx, [rcx+38h]
0x180003804  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18000380b  mov     edx, 39h ; '9'
0x180003810  call    WPP_SF_
0x180003815  mov     rcx, cs:WPP_GLOBAL_Control
0x18000381c  xor     edi, edi
0x18000381e  mov     [r14], edi
0x180003821  mov     [rsi], edi
0x180003823  cmp     rcx, rbp
0x180003826  jz      short loc_18000384D
0x180003828  test    dword ptr [rcx+44h], 800h
0x18000382f  jz      short loc_18000384D
0x180003831  mov     rcx, [rcx+38h]
0x180003835  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18000383c  mov     edx, 36h ; '6'
0x180003841  call    WPP_SF_
0x180003846  mov     rcx, cs:WPP_GLOBAL_Control
0x18000384d  test    rbx, rbx
0x180003850  jnz     short loc_180003884
0x180003852  mov     edi, 6
0x180003857  cmp     rcx, rbp
0x18000385a  jz      loc_180003943
0x180003860  test    byte ptr [rcx+44h], 1
0x180003864  jz      loc_180003916
0x18000386a  mov     rcx, [rcx+38h]
0x18000386e  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x180003875  mov     edx, 37h ; '7'
0x18000387a  call    WPP_SF_
0x18000387f  jmp     loc_18000390F
0x180003884  mov     r9d, 279h
0x18000388a  lea     r8, aPortmgrvalidat_0; "PortMgrValidateAndRefPort"
0x180003891  lea     rdx, qword_18003DD98
0x180003898  lea     rcx, g_OneXInfo
0x18000389f  call    cs:__imp_AcquireWriteLock
0x1800038a5  mov     rax, cs:qword_18003DD68
0x1800038ac  lea     rcx, qword_18003DD68
0x1800038b3  cmp     rax, rcx
0x1800038b6  jz      short loc_1800038E9
0x1800038b8  cmp     rbx, rax
0x1800038bb  jz      short loc_1800038C2
0x1800038bd  mov     rax, [rax]
0x1800038c0  jmp     short loc_1800038B3
0x1800038c2  lock inc dword ptr [rax+10h]
0x1800038c6  mov     r9d, 28Ah
0x1800038cc  lea     r8, aPortmgrvalidat_0; "PortMgrValidateAndRefPort"
0x1800038d3  lea     rdx, qword_18003DD98
0x1800038da  lea     rcx, g_OneXInfo
0x1800038e1  call    cs:__imp_ReleaseWriteLock
0x1800038e7  jmp     short loc_18000390F
0x1800038e9  mov     r9d, 28Ah
0x1800038ef  lea     r8, aPortmgrvalidat_0; "PortMgrValidateAndRefPort"
0x1800038f6  lea     rdx, qword_18003DD98
0x1800038fd  lea     rcx, g_OneXInfo
0x180003904  call    cs:__imp_ReleaseWriteLock
0x18000390a  mov     edi, 6
0x18000390f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003916  cmp     rcx, rbp
0x180003919  jz      short loc_180003943
0x18000391b  test    dword ptr [rcx+44h], 800h
0x180003922  jz      short loc_180003943
0x180003924  mov     rcx, [rcx+38h]
0x180003928  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18000392f  mov     edx, 38h ; '8'
0x180003934  mov     r9d, edi
0x180003937  call    WPP_SF_D
0x18000393c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003943  test    edi, edi
0x180003945  jz      short loc_180003979
0x180003947  cmp     rcx, rbp
0x18000394a  jz      loc_180003A06
0x180003950  test    byte ptr [rcx+44h], 1
0x180003954  jz      loc_1800039E0
0x18000395a  mov     rcx, [rcx+38h]
0x18000395e  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x180003965  mov     edx, 3Ah ; ':'
0x18000396a  mov     [rsp+58h+var_38], rbx
0x18000396f  mov     r9d, edi
0x180003972  call    WPP_SF_dq
0x180003977  jmp     short loc_1800039D9
0x180003979  lea     rdx, [rbx+0B50h]
0x180003980  mov     dword ptr [r14], 1
0x180003987  mov     r9d, 2A4h
0x18000398d  lea     r8, aPortmgrvalidat; "PortMgrValidateRefAndLockPort"
0x180003994  mov     rcx, rbx
0x180003997  call    cs:__imp_AcquireWriteLock
0x18000399d  cmp     dword ptr [rbx+18h], 0
0x1800039a1  mov     dword ptr [rsi], 1
0x1800039a7  jge     short loc_1800039D9
0x1800039a9  mov     edi, 6
0x1800039ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800039b5  cmp     rcx, rbp
0x1800039b8  jz      short loc_180003A06
0x1800039ba  test    byte ptr [rcx+44h], 1
0x1800039be  jz      short loc_1800039E0
0x1800039c0  mov     r9d, [rbx+14h]
0x1800039c4  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x1800039cb  mov     rcx, [rcx+38h]
0x1800039cf  mov     edx, 3Bh ; ';'
0x1800039d4  call    WPP_SF_d
0x1800039d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800039e0  cmp     rcx, rbp
0x1800039e3  jz      short loc_180003A06
0x1800039e5  test    dword ptr [rcx+44h], 800h
0x1800039ec  jz      short loc_180003A06
0x1800039ee  mov     rcx, [rcx+38h]
0x1800039f2  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x1800039f9  mov     edx, 3Ch ; '<'
0x1800039fe  mov     r9d, edi
0x180003a01  call    WPP_SF_D
0x180003a06  mov     eax, edi
0x180003a08  add     rsp, 30h
0x180003a0c  pop     r14
0x180003a0e  pop     rdi
0x180003a0f  pop     rsi
0x180003a10  pop     rbp
0x180003a11  pop     rbx
0x180003a12  retn
```
