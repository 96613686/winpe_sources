# TpiDispatchCreate

- ea: `0x1400034d0`
- end: `0x14000373f`
- name: `TpiDispatchCreate`
- size: `623`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140002bd8`
- `0x140002c08`
- `0x1400034d0`
- `0x140004a74`
- `0x140005110`
- `0x140005e10`
- `0x14000f58c`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400036e6`
- `ntoskrnl!IofCompleteRequest` at `0x1400036e6`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400035d1`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400035d1`
- `NDIS!NdisAllocateNetBufferListPool` at `0x14000367d`
- `NDIS!NdisAllocateNetBufferListPool` at `0x14000367d`

## pseudocode

```c
__int64 __fastcall TpiDispatchCreate(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  unsigned int v5; // ebx
  PFILE_OBJECT FileObject; // rcx
  _QWORD *v7; // rbx
  _QWORD *v8; // r14
  char v10[8]; // [rsp+20h] [rbp-58h] BYREF
  __int128 v11; // [rsp+28h] [rbp-50h] BYREF
  __int128 v12; // [rsp+38h] [rbp-40h] BYREF
  __int64 (__fastcall *v13)(); // [rsp+48h] [rbp-30h]
  __int64 (__fastcall *v14)(); // [rsp+50h] [rbp-28h]
  _NET_BUFFER_LIST_POOL_PARAMETERS Parameters; // [rsp+58h] [rbp-20h] BYREF

  v11 = 0;
  Parameters = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x82) == 0x82 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 87, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
  if ( a1 == *((_QWORD *)SstpGlobals + 1) )
  {
    CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
    v5 = 0;
    v10[0] = 0;
    if ( IsValidToken(*(_QWORD *)(CurrentStackLocation->Parameters.WMI.ProviderId + 8), v10) )
    {
      FileObject = CurrentStackLocation->FileObject;
      if ( v10[0] )
      {
        *((_QWORD *)SstpGlobals + 2) = FileObject;
        v7 = SstpGlobals;
        HIDWORD(v11) = 0;
        BYTE8(v11) = 3;
        *(_QWORD *)&v11 = *((_QWORD *)SstpGlobals + 64);
        *((_QWORD *)&v12 + 1) = TpiFsmDisconnectComplete;
        *(_QWORD *)&v12 = TpiFsmNewCallComplete;
        v13 = TpiFsmSendControlFrame;
        v14 = TpiFsmCryptoBindingComplete;
        v7[54] = IoGetCurrentProcess();
        v5 = RegisterTPIWithFsm(&v12, &v11, *((struct _DEVICE_OBJECT **)SstpGlobals + 1), (_QWORD *)SstpGlobals + 65);
        if ( v5
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 88, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
        }
      }
      else
      {
        *((_QWORD *)SstpGlobals + 3) = FileObject;
      }
      v8 = SstpGlobals;
      if ( !*((_QWORD *)SstpGlobals + 72) )
      {
        Parameters.Header = (NDIS_OBJECT_HEADER)1048960;
        Parameters.fAllocateNetBuffer = 1;
        Parameters.PoolTag = 1935961683;
        Parameters.DataSize = 4095;
        v8[72] = NdisAllocateNetBufferListPool(*((NDIS_HANDLE *)SstpGlobals + 21), &Parameters);
        if ( !*((_QWORD *)SstpGlobals + 72) )
        {
          if ( v10[0] )
            DeregisterTPIFromFsm();
          v5 = -1073741670;
        }
      }
      if ( v10[0] && *((_QWORD *)SstpGlobals + 72) )
        *((_BYTE *)SstpGlobals + 568) = 1;
    }
  }
  else
  {
    v5 = -1073741637;
  }
  a2->IoStatus.Status = v5;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x82) == 0x82 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 89, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
  return v5;
}

```

## disassembly

```asm
0x1400034d0  push    rbp
0x1400034d2  push    rbx
0x1400034d3  push    rdi
0x1400034d4  push    r14
0x1400034d6  mov     rbp, rsp
0x1400034d9  sub     rsp, 78h
0x1400034dd  mov     rax, cs:__security_cookie
0x1400034e4  xor     rax, rsp
0x1400034e7  mov     [rbp+var_10], rax
0x1400034eb  xorps   xmm0, xmm0
0x1400034ee  xorps   xmm1, xmm1
0x1400034f1  movups  [rbp+var_50], xmm0
0x1400034f5  mov     rdi, rdx
0x1400034f8  mov     rbx, rcx
0x1400034fb  movups  xmmword ptr [rbp+Parameters.Header.Type], xmm1
0x1400034ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140003506  lea     rax, WPP_GLOBAL_Control
0x14000350d  cmp     rcx, rax
0x140003510  jz      short loc_140003533
0x140003512  mov     eax, [rcx+2Ch]
0x140003515  and     eax, 82h
0x14000351a  cmp     al, 82h
0x14000351c  jnz     short loc_140003533
0x14000351e  mov     rcx, [rcx+18h]
0x140003522  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140003529  mov     edx, 57h ; 'W'
0x14000352e  call    WPP_SF_
0x140003533  mov     rax, cs:SstpGlobals
0x14000353a  cmp     rbx, [rax+8]
0x14000353e  jnz     loc_1400036D1
0x140003544  mov     r14, [rdi+0B8h]
0x14000354b  lea     rdx, [rbp+var_58]
0x14000354f  xor     ebx, ebx
0x140003551  mov     [rbp+var_58], bl
0x140003554  mov     rcx, [r14+8]
0x140003558  mov     rcx, [rcx+8]
0x14000355c  call    IsValidToken
0x140003561  test    al, al
0x140003563  jz      loc_1400036D6
0x140003569  mov     rcx, [r14+30h]
0x14000356d  mov     rax, cs:SstpGlobals
0x140003574  cmp     [rbp+var_58], bl
0x140003577  jz      loc_140003644
0x14000357d  mov     [rax+10h], rcx
0x140003581  mov     rbx, cs:SstpGlobals
0x140003588  mov     dword ptr [rbp+var_50+0Ch], 0
0x14000358f  mov     byte ptr [rbp+var_50+8], 3
0x140003593  mov     eax, [rbx+204h]
0x140003599  mov     dword ptr [rbp+var_50+4], eax
0x14000359c  mov     eax, [rbx+200h]
0x1400035a2  mov     dword ptr [rbp+var_50], eax
0x1400035a5  lea     rax, TpiFsmDisconnectComplete
0x1400035ac  mov     [rbp+var_38], rax
0x1400035b0  lea     rax, TpiFsmNewCallComplete
0x1400035b7  mov     [rbp+var_40], rax
0x1400035bb  lea     rax, TpiFsmSendControlFrame
0x1400035c2  mov     [rbp+var_30], rax
0x1400035c6  lea     rax, TpiFsmCryptoBindingComplete
0x1400035cd  mov     [rbp+var_28], rax
0x1400035d1  call    cs:__imp_IoGetCurrentProcess
0x1400035d8  nop     dword ptr [rax+rax+00h]
0x1400035dd  mov     [rbx+1B0h], rax
0x1400035e4  lea     rdx, [rbp+var_50]
0x1400035e8  mov     r8, cs:SstpGlobals
0x1400035ef  lea     rcx, [rbp+var_40]
0x1400035f3  lea     r9, [r8+208h]
0x1400035fa  mov     r8, [r8+8]
0x1400035fe  call    RegisterTPIWithFsm
0x140003603  mov     ebx, eax
0x140003605  test    eax, eax
0x140003607  jz      short loc_140003648
0x140003609  mov     rcx, cs:WPP_GLOBAL_Control
0x140003610  lea     rax, WPP_GLOBAL_Control
0x140003617  cmp     rcx, rax
0x14000361a  jz      short loc_140003648
0x14000361c  mov     edx, [rcx+2Ch]
0x14000361f  test    dl, 2
0x140003622  jz      short loc_140003648
0x140003624  cmp     byte ptr [rcx+29h], 1
0x140003628  jb      short loc_140003648
0x14000362a  mov     rcx, [rcx+18h]
0x14000362e  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140003635  mov     edx, 58h ; 'X'
0x14000363a  mov     r9d, ebx
0x14000363d  call    WPP_SF_d
0x140003642  jmp     short loc_140003648
0x140003644  mov     [rax+18h], rcx
0x140003648  mov     r14, cs:SstpGlobals
0x14000364f  cmp     qword ptr [r14+240h], 0
0x140003657  jnz     short loc_1400036B1
0x140003659  mov     dword ptr [rbp+Parameters.Header.Type], 100180h
0x140003660  lea     rdx, [rbp+Parameters]; Parameters
0x140003664  mov     [rbp+Parameters.fAllocateNetBuffer], 1
0x140003668  mov     [rbp+Parameters.PoolTag], 73646E53h
0x14000366f  mov     [rbp+Parameters.DataSize], 0FFFh
0x140003676  mov     rcx, [r14+0A8h]; NdisHandle
0x14000367d  call    cs:__imp_NdisAllocateNetBufferListPool
0x140003684  nop     dword ptr [rax+rax+00h]
0x140003689  mov     [r14+240h], rax
0x140003690  mov     rax, cs:SstpGlobals
0x140003697  cmp     qword ptr [rax+240h], 0
0x14000369f  jnz     short loc_1400036B1
0x1400036a1  cmp     [rbp+var_58], 0
0x1400036a5  jz      short loc_1400036AC
0x1400036a7  call    DeregisterTPIFromFsm
0x1400036ac  mov     ebx, 0C000009Ah
0x1400036b1  cmp     [rbp+var_58], 0
0x1400036b5  jz      short loc_1400036D6
0x1400036b7  mov     rax, cs:SstpGlobals
0x1400036be  cmp     qword ptr [rax+240h], 0
0x1400036c6  jz      short loc_1400036D6
0x1400036c8  mov     byte ptr [rax+238h], 1
0x1400036cf  jmp     short loc_1400036D6
0x1400036d1  mov     ebx, 0C00000BBh
0x1400036d6  xor     edx, edx; PriorityBoost
0x1400036d8  mov     [rdi+30h], ebx
0x1400036db  mov     rcx, rdi; Irp
0x1400036de  mov     qword ptr [rdi+38h], 0
0x1400036e6  call    cs:__imp_IofCompleteRequest
0x1400036ed  nop     dword ptr [rax+rax+00h]
0x1400036f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400036f9  lea     rax, WPP_GLOBAL_Control
0x140003700  cmp     rcx, rax
0x140003703  jz      short loc_140003726
0x140003705  mov     eax, [rcx+2Ch]
0x140003708  and     eax, 82h
0x14000370d  cmp     al, 82h
0x14000370f  jnz     short loc_140003726
0x140003711  mov     rcx, [rcx+18h]
0x140003715  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x14000371c  mov     edx, 59h ; 'Y'
0x140003721  call    WPP_SF_
0x140003726  mov     eax, ebx
0x140003728  mov     rcx, [rbp+var_10]
0x14000372c  xor     rcx, rsp; StackCookie
0x14000372f  call    __security_check_cookie
0x140003734  add     rsp, 78h
0x140003738  pop     r14
0x14000373a  pop     rdi
0x14000373b  pop     rbx
0x14000373c  pop     rbp
0x14000373d  retn
```
