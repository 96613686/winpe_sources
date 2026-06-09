# CMsftWriteEngine2::WaitForTaskOrKillSignal(uchar)

- ea: `0x1800361c8`
- end: `0x1800365be`
- name: `?WaitForTaskOrKillSignal@CMsftWriteEngine2@@QEAAJE@Z`
- size: `1014`
- prototype: `__int64 __fastcall(CMsftWriteEngine2 *__hidden this, unsigned __int8)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180036150`
- `0x180036190`

## callees

- `0x180008510`
- `0x18000b510`
- `0x1800140f4`
- `0x180016778`
- `0x1800361c8`

## import_xrefs

- `USER32!MsgWaitForMultipleObjects` at `0x180036237`
- `USER32!MsgWaitForMultipleObjects` at `0x180036237`
- `KERNEL32!WaitForSingleObject` at `0x18003631f`
- `KERNEL32!WaitForSingleObject` at `0x18003631f`
- `KERNEL32!SetEvent` at `0x1800361f0`
- `KERNEL32!SetEvent` at `0x1800362dd`
- `KERNEL32!SetEvent` at `0x18003649f`
- `KERNEL32!SetEvent` at `0x180036546`
- `KERNEL32!SetEvent` at `0x1800361f0`
- `KERNEL32!SetEvent` at `0x1800362dd`
- `KERNEL32!SetEvent` at `0x18003649f`
- `KERNEL32!SetEvent` at `0x180036546`
- `KERNEL32!ResetEvent` at `0x1800362d0`
- `KERNEL32!ResetEvent` at `0x180036539`
- `KERNEL32!ResetEvent` at `0x1800362d0`
- `KERNEL32!ResetEvent` at `0x180036539`

## pseudocode

```c
__int64 __fastcall CMsftWriteEngine2::WaitForTaskOrKillSignal(CMsftWriteEngine2 *this, char a2)
{
  DWORD v4; // eax
  unsigned __int32 v5; // ebx
  PVOID *v6; // rcx
  void *v7; // rcx
  PVOID *v8; // rcx
  unsigned int v9; // eax
  int v10; // ebx
  PVOID *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rdx
  _DWORD *v14; // rbx
  unsigned __int32 v15; // edi
  PVOID *v16; // rcx
  void *v17; // rcx
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  HANDLE pHandles[9]; // [rsp+30h] [rbp-48h] BYREF

  SetEvent(*(HANDLE *)((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFE8uLL) + 232));
  while ( 1 )
  {
    pHandles[0] = *((HANDLE *)this + 24);
    pHandles[1] = *((HANDLE *)this + 21);
    v4 = MsgWaitForMultipleObjects(2u, pHandles, 0, 0xFFFFFFFF, 0);
    if ( !v4 )
      break;
    if ( v4 == 1 )
    {
      v5 = _InterlockedIncrement((volatile signed __int32 *)this + 40);
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 30, &WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids, v5);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v5 == 2 )
      {
        if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 228) & 4) != 0 && *((_BYTE *)v6 + 225) >= 4u )
          WPP_SF_(v6[27], 31, &WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids);
        v7 = (void *)*((_QWORD *)this + 21);
        *((_QWORD *)this + 20) = 0;
        ResetEvent(v7);
        SetEvent(*((HANDLE *)this + 22));
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 228) & 4) != 0 && *((_BYTE *)v6 + 225) >= 4u )
        WPP_SF_(v6[27], 32, &WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids);
      WaitForSingleObject(*((HANDLE *)this + 22), 0xFFFFFFFF);
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 33, &WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( a2 )
      {
        if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 228) & 4) != 0 && *((_BYTE *)v8 + 225) >= 4u )
          WPP_SF_(v8[27], 34, &WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids);
        v9 = CMsftWriteEngine2::ReadFromStream(this);
        v10 = v9;
        *((_DWORD *)this + 38) = v9;
        v11 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u )
        {
          v12 = 35;
LABEL_39:
          WPP_SF_d(v11[27], v12, &WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids, v9);
          v11 = (PVOID *)WPP_GLOBAL_Control;
        }
      }
      else
      {
        if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 228) & 4) != 0 && *((_BYTE *)v8 + 225) >= 4u )
          WPP_SF_(v8[27], 36, &WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids);
        v9 = CMsftWriteEngine2::WriteToRecorder(this);
        v10 = v9;
        *((_DWORD *)this + 39) = v9;
        v11 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u )
        {
          v12 = 37;
          goto LABEL_39;
        }
      }
      if ( v10 < 0 )
      {
        if ( a2 )
        {
          if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 228) & 4) != 0 && *((_BYTE *)v11 + 225) >= 3u )
          {
            v13 = 38;
            goto LABEL_50;
          }
        }
        else if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 228) & 4) != 0 && *((_BYTE *)v11 + 225) >= 3u )
        {
          v13 = 39;
LABEL_50:
          WPP_SF_(v11[27], v13, &WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids);
        }
        SetEvent(*(HANDLE *)(*((_QWORD *)this + 16) + 56LL));
      }
      v14 = (_DWORD *)((char *)this + 164);
      v15 = _InterlockedIncrement((volatile signed __int32 *)this + 41);
      v16 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 40, &WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids, v15);
        v16 = (PVOID *)WPP_GLOBAL_Control;
        v14 = (_DWORD *)((char *)this + 164);
      }
      if ( v15 == 2 )
      {
        if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 228) & 4) != 0 && *((_BYTE *)v16 + 225) >= 4u )
          WPP_SF_(v16[27], 41, &WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids);
        v17 = (void *)*((_QWORD *)this + 22);
        *v14 = 0;
        ResetEvent(v17);
        SetEvent(*((HANDLE *)this + 23));
      }
    }
  }
  if ( a2 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 2u )
    {
      v19 = 28;
      goto LABEL_71;
    }
  }
  else
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 2u )
    {
      v19 = 29;
LABEL_71:
      WPP_SF_(v18[27], v19, &WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800361c8  push    rbx
0x1800361ca  push    rbp
0x1800361cb  push    rsi
0x1800361cc  push    rdi
0x1800361cd  push    r12
0x1800361cf  push    r14
0x1800361d1  push    r15
0x1800361d3  sub     rsp, 40h
0x1800361d7  mov     rsi, rcx
0x1800361da  mov     al, dl
0x1800361dc  neg     al
0x1800361de  mov     bpl, dl
0x1800361e1  sbb     rcx, rcx
0x1800361e4  and     rcx, 0FFFFFFFFFFFFFFE8h
0x1800361e8  mov     rcx, [rcx+rsi+0E8h]; hEvent
0x1800361f0  call    cs:__imp_SetEvent
0x1800361f6  lea     r15, WPP_GLOBAL_Control
0x1800361fd  mov     r14b, 4
0x180036200  lea     r12, WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids
0x180036207  mov     rax, [rsi+0C0h]
0x18003620e  lea     rdx, [rsp+78h+pHandles]; pHandles
0x180036213  xor     r8d, r8d; fWaitAll
0x180036216  mov     [rsp+78h+pHandles], rax
0x18003621b  mov     rax, [rsi+0A8h]
0x180036222  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180036226  mov     [rsp+78h+var_40], rax
0x18003622b  mov     [rsp+78h+dwWakeMask], 0; dwWakeMask
0x180036233  lea     ecx, [r8+2]; nCount
0x180036237  call    cs:__imp_MsgWaitForMultipleObjects
0x18003623d  test    eax, eax
0x18003623f  jz      loc_180036551
0x180036245  cmp     eax, 1
0x180036248  jnz     short loc_180036207
0x18003624a  mov     ebx, eax
0x18003624c  lock xadd [rsi+0A0h], ebx
0x180036254  inc     ebx
0x180036256  mov     rcx, cs:WPP_GLOBAL_Control
0x18003625d  cmp     rcx, r15
0x180036260  jz      short loc_180036290
0x180036262  test    [rcx+0E4h], r14b
0x180036269  jz      short loc_180036290
0x18003626b  cmp     [rcx+0E1h], r14b
0x180036272  jb      short loc_180036290
0x180036274  mov     rcx, [rcx+0D8h]
0x18003627b  lea     edx, [rax+1Dh]
0x18003627e  mov     r9d, ebx
0x180036281  mov     r8, r12
0x180036284  call    WPP_SF_d
0x180036289  mov     rcx, cs:WPP_GLOBAL_Control
0x180036290  cmp     ebx, 2
0x180036293  jnz     short loc_1800362EA
0x180036295  cmp     rcx, r15
0x180036298  jz      short loc_1800362BE
0x18003629a  test    [rcx+0E4h], r14b
0x1800362a1  jz      short loc_1800362BE
0x1800362a3  cmp     [rcx+0E1h], r14b
0x1800362aa  jb      short loc_1800362BE
0x1800362ac  mov     rcx, [rcx+0D8h]
0x1800362b3  lea     edx, [rbx+1Dh]
0x1800362b6  mov     r8, r12
0x1800362b9  call    WPP_SF_
0x1800362be  mov     rcx, [rsi+0A8h]; hEvent
0x1800362c5  mov     qword ptr [rsi+0A0h], 0
0x1800362d0  call    cs:__imp_ResetEvent
0x1800362d6  mov     rcx, [rsi+0B0h]; hEvent
0x1800362dd  call    cs:__imp_SetEvent
0x1800362e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800362ea  cmp     rcx, r15
0x1800362ed  jz      short loc_180036315
0x1800362ef  test    [rcx+0E4h], r14b
0x1800362f6  jz      short loc_180036315
0x1800362f8  cmp     [rcx+0E1h], r14b
0x1800362ff  jb      short loc_180036315
0x180036301  mov     rcx, [rcx+0D8h]
0x180036308  mov     edx, 20h ; ' '
0x18003630d  mov     r8, r12
0x180036310  call    WPP_SF_
0x180036315  mov     rcx, [rsi+0B0h]; hHandle
0x18003631c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003631f  call    cs:__imp_WaitForSingleObject
0x180036325  mov     rcx, cs:WPP_GLOBAL_Control
0x18003632c  cmp     rcx, r15
0x18003632f  jz      short loc_18003635E
0x180036331  test    [rcx+0E4h], r14b
0x180036338  jz      short loc_18003635E
0x18003633a  cmp     [rcx+0E1h], r14b
0x180036341  jb      short loc_18003635E
0x180036343  mov     rcx, [rcx+0D8h]
0x18003634a  mov     edx, 21h ; '!'
0x18003634f  mov     r8, r12
0x180036352  call    WPP_SF_
0x180036357  mov     rcx, cs:WPP_GLOBAL_Control
0x18003635e  test    bpl, bpl
0x180036361  jz      short loc_1800363CB
0x180036363  cmp     rcx, r15
0x180036366  jz      short loc_18003638E
0x180036368  test    [rcx+0E4h], r14b
0x18003636f  jz      short loc_18003638E
0x180036371  cmp     [rcx+0E1h], r14b
0x180036378  jb      short loc_18003638E
0x18003637a  mov     rcx, [rcx+0D8h]
0x180036381  mov     edx, 22h ; '"'
0x180036386  mov     r8, r12
0x180036389  call    WPP_SF_
0x18003638e  mov     rcx, rsi; this
0x180036391  call    ?ReadFromStream@CMsftWriteEngine2@@QEAAJXZ; CMsftWriteEngine2::ReadFromStream(void)
0x180036396  mov     ebx, eax
0x180036398  mov     [rsi+98h], eax
0x18003639e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800363a5  cmp     rcx, r15
0x1800363a8  jz      loc_180036442
0x1800363ae  test    [rcx+0E4h], r14b
0x1800363b5  jz      loc_180036442
0x1800363bb  cmp     [rcx+0E1h], r14b
0x1800363c2  jb      short loc_180036442
0x1800363c4  mov     edx, 23h ; '#'
0x1800363c9  jmp     short loc_180036429
0x1800363cb  cmp     rcx, r15
0x1800363ce  jz      short loc_1800363F6
0x1800363d0  test    [rcx+0E4h], r14b
0x1800363d7  jz      short loc_1800363F6
0x1800363d9  cmp     [rcx+0E1h], r14b
0x1800363e0  jb      short loc_1800363F6
0x1800363e2  mov     rcx, [rcx+0D8h]
0x1800363e9  mov     edx, 24h ; '$'
0x1800363ee  mov     r8, r12
0x1800363f1  call    WPP_SF_
0x1800363f6  mov     rcx, rsi; this
0x1800363f9  call    ?WriteToRecorder@CMsftWriteEngine2@@QEAAJXZ; CMsftWriteEngine2::WriteToRecorder(void)
0x1800363fe  mov     ebx, eax
0x180036400  mov     [rsi+9Ch], eax
0x180036406  mov     rcx, cs:WPP_GLOBAL_Control
0x18003640d  cmp     rcx, r15
0x180036410  jz      short loc_180036442
0x180036412  test    [rcx+0E4h], r14b
0x180036419  jz      short loc_180036442
0x18003641b  cmp     [rcx+0E1h], r14b
0x180036422  jb      short loc_180036442
0x180036424  mov     edx, 25h ; '%'
0x180036429  mov     rcx, [rcx+0D8h]
0x180036430  mov     r9d, eax
0x180036433  mov     r8, r12
0x180036436  call    WPP_SF_d
0x18003643b  mov     rcx, cs:WPP_GLOBAL_Control
0x180036442  test    ebx, ebx
0x180036444  jns     short loc_1800364A5
0x180036446  test    bpl, bpl
0x180036449  jz      short loc_180036469
0x18003644b  cmp     rcx, r15
0x18003644e  jz      short loc_180036494
0x180036450  test    [rcx+0E4h], r14b
0x180036457  jz      short loc_180036494
0x180036459  cmp     byte ptr [rcx+0E1h], 3
0x180036460  jb      short loc_180036494
0x180036462  mov     edx, 26h ; '&'
0x180036467  jmp     short loc_180036485
0x180036469  cmp     rcx, r15
0x18003646c  jz      short loc_180036494
0x18003646e  test    [rcx+0E4h], r14b
0x180036475  jz      short loc_180036494
0x180036477  cmp     byte ptr [rcx+0E1h], 3
0x18003647e  jb      short loc_180036494
0x180036480  mov     edx, 27h ; '''
0x180036485  mov     rcx, [rcx+0D8h]
0x18003648c  mov     r8, r12
0x18003648f  call    WPP_SF_
0x180036494  mov     rcx, [rsi+80h]
0x18003649b  mov     rcx, [rcx+38h]; hEvent
0x18003649f  call    cs:__imp_SetEvent
0x1800364a5  lea     rbx, [rsi+0A4h]
0x1800364ac  mov     edi, 1
0x1800364b1  lock xadd [rbx], edi
0x1800364b5  inc     edi
0x1800364b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800364be  cmp     rcx, r15
0x1800364c1  jz      short loc_1800364FA
0x1800364c3  test    [rcx+0E4h], r14b
0x1800364ca  jz      short loc_1800364FA
0x1800364cc  cmp     [rcx+0E1h], r14b
0x1800364d3  jb      short loc_1800364FA
0x1800364d5  mov     rcx, [rcx+0D8h]
0x1800364dc  mov     edx, 28h ; '('
0x1800364e1  mov     r9d, edi
0x1800364e4  mov     r8, r12
0x1800364e7  call    WPP_SF_d
0x1800364ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800364f3  lea     rbx, [rsi+0A4h]
0x1800364fa  cmp     edi, 2
0x1800364fd  jnz     loc_180036207
0x180036503  cmp     rcx, r15
0x180036506  jz      short loc_18003652C
0x180036508  test    [rcx+0E4h], r14b
0x18003650f  jz      short loc_18003652C
0x180036511  cmp     [rcx+0E1h], r14b
0x180036518  jb      short loc_18003652C
0x18003651a  mov     rcx, [rcx+0D8h]
0x180036521  lea     edx, [rdi+27h]
0x180036524  mov     r8, r12
0x180036527  call    WPP_SF_
0x18003652c  mov     rcx, [rsi+0B0h]; hEvent
0x180036533  mov     dword ptr [rbx], 0
0x180036539  call    cs:__imp_ResetEvent
0x18003653f  mov     rcx, [rsi+0B8h]; hEvent
0x180036546  call    cs:__imp_SetEvent
0x18003654c  jmp     loc_180036207
0x180036551  test    bpl, bpl
0x180036554  jz      short loc_18003657B
0x180036556  mov     rcx, cs:WPP_GLOBAL_Control
0x18003655d  cmp     rcx, r15
0x180036560  jz      short loc_1800365AD
0x180036562  test    [rcx+0E4h], r14b
0x180036569  jz      short loc_1800365AD
0x18003656b  cmp     byte ptr [rcx+0E1h], 2
0x180036572  jb      short loc_1800365AD
0x180036574  mov     edx, 1Ch
0x180036579  jmp     short loc_18003659E
0x18003657b  mov     rcx, cs:WPP_GLOBAL_Control
0x180036582  cmp     rcx, r15
0x180036585  jz      short loc_1800365AD
0x180036587  test    [rcx+0E4h], r14b
0x18003658e  jz      short loc_1800365AD
0x180036590  cmp     byte ptr [rcx+0E1h], 2
0x180036597  jb      short loc_1800365AD
0x180036599  mov     edx, 1Dh
0x18003659e  mov     rcx, [rcx+0D8h]
0x1800365a5  mov     r8, r12
0x1800365a8  call    WPP_SF_
0x1800365ad  xor     eax, eax
0x1800365af  add     rsp, 40h
0x1800365b3  pop     r15
0x1800365b5  pop     r14
0x1800365b7  pop     r12
0x1800365b9  pop     rdi
0x1800365ba  pop     rsi
0x1800365bb  pop     rbp
0x1800365bc  pop     rbx
0x1800365bd  retn
```
