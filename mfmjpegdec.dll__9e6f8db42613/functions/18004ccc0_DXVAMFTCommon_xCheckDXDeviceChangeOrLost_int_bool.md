# DXVAMFTCommon::xCheckDXDeviceChangeOrLost(int,bool *)

- ea: `0x18004ccc0`
- end: `0x18004ce08`
- name: `?xCheckDXDeviceChangeOrLost@DXVAMFTCommon@@UEAAJHPEA_N@Z`
- size: `328`
- prototype: `__int64 __fastcall(DXVAMFTCommon *__hidden this, int, bool *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180044d78`
- `0x18004ca78`
- `0x18004ccc0`
- `0x18004d23c`
- `0x1800533c0`
- `0x180070010`

## pseudocode

```c
__int64 __fastcall DXVAMFTCommon::xCheckDXDeviceChangeOrLost(DXVAMFTCommon *this, int a2, bool *a3)
{
  unsigned int v7; // esi
  __int64 v8; // rcx
  char v9; // bp
  __int64 v10; // rcx
  __int64 v11; // rcx
  bool v12; // [rsp+40h] [rbp+8h] BYREF
  bool v13; // [rsp+50h] [rbp+18h] BYREF

  v13 = 0;
  v12 = 0;
  if ( a3 )
    *a3 = 0;
  if ( !*((_DWORD *)this + 85) && !*((_DWORD *)this + 86) )
    return 0;
  v7 = DXVAMFTCommon::xCheckDXAdapterChanged(this, &v12, &v13);
  if ( !v7
    && (v12
     || v13
     || (v8 = *((_QWORD *)this + 1)) != 0 && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8)) )
  {
    if ( g_wppLevels >= 4u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids, this);
    v9 = 1;
    if ( a3 )
      *a3 = 1;
    (*(void (__fastcall **)(DXVAMFTCommon *))(*(_QWORD *)this + 24LL))(this);
    if ( a2 )
    {
      v10 = *((_QWORD *)this + 49);
      if ( v10 )
        CDXVAFrameManager::Cleanup(v10, 2, 0);
      v11 = *((_QWORD *)this + 1);
      if ( v11 )
      {
        v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
        if ( !v7 )
        {
          if ( *((_QWORD *)this + 50) )
          {
            if ( !v12 && !v13 )
              v9 = 0;
            DXVAMFTCommon::xReopenDeviceManager(this, v9);
          }
        }
      }
    }
    else
    {
      return (unsigned int)-2147217407;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18004ccc0  mov     rax, rsp
0x18004ccc3  mov     [rax+10h], rbx
0x18004ccc7  mov     [rax+20h], rbp
0x18004cccb  push    rsi
0x18004cccc  push    rdi
0x18004cccd  push    r12
0x18004cccf  sub     rsp, 20h
0x18004ccd3  mov     byte ptr [rax+18h], 0
0x18004ccd7  mov     rdi, r8
0x18004ccda  mov     byte ptr [rax+8], 0
0x18004ccde  mov     r12d, edx
0x18004cce1  mov     rbx, rcx
0x18004cce4  test    r8, r8
0x18004cce7  jz      short loc_18004CCED
0x18004cce9  mov     byte ptr [r8], 0
0x18004cced  cmp     dword ptr [rcx+154h], 0
0x18004ccf4  jnz     short loc_18004CD06
0x18004ccf6  cmp     dword ptr [rcx+158h], 0
0x18004ccfd  jnz     short loc_18004CD06
0x18004ccff  xor     eax, eax
0x18004cd01  jmp     loc_18004CDF5
0x18004cd06  lea     r8, [rsp+38h+arg_10]; bool *
0x18004cd0b  lea     rdx, [rsp+38h+arg_0]; bool *
0x18004cd10  call    ?xCheckDXAdapterChanged@DXVAMFTCommon@@AEAAJPEA_N0@Z; DXVAMFTCommon::xCheckDXAdapterChanged(bool *,bool *)
0x18004cd15  mov     esi, eax
0x18004cd17  test    eax, eax
0x18004cd19  jnz     loc_18004CDF3
0x18004cd1f  cmp     [rsp+38h+arg_0], al
0x18004cd23  jnz     short loc_18004CD4C
0x18004cd25  cmp     [rsp+38h+arg_10], al
0x18004cd29  jnz     short loc_18004CD4C
0x18004cd2b  mov     rcx, [rbx+8]
0x18004cd2f  test    rcx, rcx
0x18004cd32  jz      loc_18004CDF3
0x18004cd38  mov     rax, [rcx]
0x18004cd3b  mov     rax, [rax+10h]
0x18004cd3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cd44  test    eax, eax
0x18004cd46  jz      loc_18004CDF3
0x18004cd4c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 4; MFWppLevels g_wppLevels
0x18004cd53  jb      short loc_18004CD74
0x18004cd55  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cd5c  lea     r8, WPP_f67d1fe5fbab32c956b7538a857ac501_Traceguids
0x18004cd63  mov     edx, 1Fh
0x18004cd68  mov     r9, rbx
0x18004cd6b  mov     rcx, [rcx+10h]
0x18004cd6f  call    WPP_SF_q
0x18004cd74  mov     bpl, 1
0x18004cd77  test    rdi, rdi
0x18004cd7a  jz      short loc_18004CD7F
0x18004cd7c  mov     [rdi], bpl
0x18004cd7f  mov     rax, [rbx]
0x18004cd82  mov     rcx, rbx
0x18004cd85  mov     rax, [rax+18h]
0x18004cd89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cd8e  test    r12d, r12d
0x18004cd91  jz      short loc_18004CDEE
0x18004cd93  mov     rcx, [rbx+188h]
0x18004cd9a  test    rcx, rcx
0x18004cd9d  jz      short loc_18004CDAE
0x18004cd9f  xor     r9d, r9d
0x18004cda2  xor     r8d, r8d
0x18004cda5  lea     edx, [r9+2]
0x18004cda9  call    ?Cleanup@CDXVAFrameManager@@UEAAJW4FRAMEMGR_CLEANUP_STATE@@PEAI1@Z; CDXVAFrameManager::Cleanup(FRAMEMGR_CLEANUP_STATE,uint *,uint *)
0x18004cdae  mov     rcx, [rbx+8]
0x18004cdb2  test    rcx, rcx
0x18004cdb5  jz      short loc_18004CDF3
0x18004cdb7  mov     rax, [rcx]
0x18004cdba  mov     rax, [rax+8]
0x18004cdbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cdc3  mov     esi, eax
0x18004cdc5  test    eax, eax
0x18004cdc7  jnz     short loc_18004CDF3
0x18004cdc9  cmp     qword ptr [rbx+190h], 0
0x18004cdd1  jz      short loc_18004CDF3
0x18004cdd3  cmp     [rsp+38h+arg_0], al
0x18004cdd7  jnz     short loc_18004CDE1
0x18004cdd9  cmp     [rsp+38h+arg_10], al
0x18004cddd  jnz     short loc_18004CDE1
0x18004cddf  xor     ebp, ebp
0x18004cde1  mov     dl, bpl; bool
0x18004cde4  mov     rcx, rbx; this
0x18004cde7  call    ?xReopenDeviceManager@DXVAMFTCommon@@AEAAJ_N@Z; DXVAMFTCommon::xReopenDeviceManager(bool)
0x18004cdec  jmp     short loc_18004CDF3
0x18004cdee  mov     esi, 80041001h
0x18004cdf3  mov     eax, esi
0x18004cdf5  mov     rbx, [rsp+38h+arg_8]
0x18004cdfa  mov     rbp, [rsp+38h+arg_18]
0x18004cdff  add     rsp, 20h
0x18004ce03  pop     r12
0x18004ce05  pop     rdi
0x18004ce06  pop     rsi
0x18004ce07  retn
```
