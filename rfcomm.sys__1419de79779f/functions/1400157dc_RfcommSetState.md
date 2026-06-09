# RfcommSetState

- ea: `0x1400157dc`
- end: `0x1400158fb`
- name: `RfcommSetState`
- size: `287`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140012590`
- `0x14001291c`
- `0x1400174a8`
- `0x140017704`
- `0x140017ab8`
- `0x140017db4`
- `0x140018e9c`
- `0x140019f70`

## callees

- `0x140003bf4`
- `0x14000e700`
- `0x1400157dc`
- `0x140015bdc`
- `0x140016ebc`

## pseudocode

```c
char __fastcall RfcommSetState(__int64 a1, int a2)
{
  __int64 v2; // rsi
  __int64 v4; // rdi
  const char *v5; // rax
  int v6; // edx
  __int64 v7; // r8
  char v8; // di

  v2 = *(int *)(a1 + 48);
  v4 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    RfcommStateTxt(a2);
    v5 = RfcommStateTxt(v2);
    WPP_RECORDER_SF_qss(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      17,
      175,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      a1,
      (__int64)v5,
      v7);
  }
  if ( *((_DWORD *)RfcommStateMatrix + 7 * v2 + v4) )
  {
    *(_DWORD *)(a1 + 48) = v4;
    v8 = 1;
    *(_DWORD *)(a1 + 188) = 0;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        1,
        176,
        (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
    if ( (_DWORD)v2 == 6 && *(_QWORD *)(a1 + 280) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          1,
          177,
          (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
      if ( !_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 480), 1, 0) )
        BrbpDisconnect((_QWORD *)a1);
    }
    return 0;
  }
  return v8;
}

```

## disassembly

```asm
0x1400157dc  push    rbx
0x1400157de  push    rsi
0x1400157df  push    rdi
0x1400157e0  push    r14
0x1400157e2  push    r15
0x1400157e4  sub     rsp, 40h
0x1400157e8  movsxd  rsi, dword ptr [rcx+30h]
0x1400157ec  mov     rbx, rcx
0x1400157ef  movsxd  rdi, edx
0x1400157f2  lea     r14, WPP_RECORDER_INITIALIZED
0x1400157f9  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140015800  lea     r15, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140015807  jz      short loc_14001584A
0x140015809  mov     ecx, edi
0x14001580b  call    RfcommStateTxt
0x140015810  mov     ecx, esi
0x140015812  mov     r8, rax
0x140015815  call    RfcommStateTxt
0x14001581a  mov     rcx, cs:WPP_GLOBAL_Control
0x140015821  mov     r9d, 0AFh
0x140015827  mov     [rsp+68h+var_30], r8
0x14001582c  mov     r8d, 11h
0x140015832  mov     [rsp+68h+var_38], rax
0x140015837  mov     [rsp+68h+var_40], rbx
0x14001583c  mov     rcx, [rcx+40h]
0x140015840  mov     [rsp+68h+var_48], r15
0x140015845  call    WPP_RECORDER_SF_qss
0x14001584a  imul    rcx, rsi, 7
0x14001584e  lea     rax, RfcommStateMatrix
0x140015855  add     rcx, rdi
0x140015858  cmp     dword ptr [rax+rcx*4], 0
0x14001585c  jnz     short loc_1400158D9
0x14001585e  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140015865  mov     edi, 1
0x14001586a  jz      short loc_14001588A
0x14001586c  mov     rcx, cs:WPP_GLOBAL_Control
0x140015873  mov     r9d, 0B0h
0x140015879  mov     r8d, edi
0x14001587c  mov     [rsp+68h+var_48], r15
0x140015881  mov     rcx, [rcx+40h]
0x140015885  call    WPP_RECORDER_SF_
0x14001588a  cmp     esi, 6
0x14001588d  jnz     short loc_1400158D4
0x14001588f  cmp     qword ptr [rbx+118h], 0
0x140015897  jz      short loc_1400158D4
0x140015899  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400158a0  jz      short loc_1400158C0
0x1400158a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400158a9  mov     r9d, 0B1h
0x1400158af  mov     r8d, edi
0x1400158b2  mov     [rsp+68h+var_48], r15
0x1400158b7  mov     rcx, [rcx+40h]
0x1400158bb  call    WPP_RECORDER_SF_
0x1400158c0  xor     eax, eax
0x1400158c2  lock cmpxchg [rbx+1E0h], edi
0x1400158ca  jnz     short loc_1400158D4
0x1400158cc  mov     rcx, rbx
0x1400158cf  call    BrbpDisconnect
0x1400158d4  xor     dil, dil
0x1400158d7  jmp     short loc_1400158EB
0x1400158d9  mov     [rbx+30h], edi
0x1400158dc  mov     edi, 1
0x1400158e1  mov     dword ptr [rbx+0BCh], 0
0x1400158eb  mov     al, dil
0x1400158ee  add     rsp, 40h
0x1400158f2  pop     r15
0x1400158f4  pop     r14
0x1400158f6  pop     rdi
0x1400158f7  pop     rsi
0x1400158f8  pop     rbx
0x1400158f9  retn
```
