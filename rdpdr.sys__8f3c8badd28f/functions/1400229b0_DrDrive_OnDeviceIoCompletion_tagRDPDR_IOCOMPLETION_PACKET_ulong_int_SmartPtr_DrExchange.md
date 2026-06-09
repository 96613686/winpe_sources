# DrDrive::OnDeviceIoCompletion(tagRDPDR_IOCOMPLETION_PACKET *,ulong,int *,SmartPtr<DrExchange> &)

- ea: `0x1400229b0`
- end: `0x140022aa5`
- name: `?OnDeviceIoCompletion@DrDrive@@UEAAJPEAUtagRDPDR_IOCOMPLETION_PACKET@@KPEAHAEAV?$SmartPtr@VDrExchange@@@@@Z`
- size: `245`
- prototype: `__int64 __fastcall(__int64, unsigned int *, unsigned int, _DWORD *, RefCount *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000324c`
- `0x1400229b0`
- `0x140022ab0`

## pseudocode

```c
__int64 __fastcall DrDrive::OnDeviceIoCompletion(
        __int64 a1,
        unsigned int *a2,
        unsigned int a3,
        _DWORD *a4,
        RefCount *a5)
{
  __int64 v9; // rax
  __int64 v10; // rcx

  v9 = *(_QWORD *)(*(_QWORD *)a5 + 32LL);
  if ( v9 )
  {
    if ( *(_BYTE *)(v9 + 56) == 13 && *(_BYTE *)(v9 + 57) == 4 )
    {
      v10 = *(_QWORD *)(v9 + 48);
      if ( v10 )
      {
        if ( *(_DWORD *)(v10 + 540) == 589980 && a2[3] == -1073741809 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 77, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
          a2[3] = -1073741072;
        }
      }
    }
    return DrDevice::OnDeviceIoCompletion(a1, a2, a3, a4, a5);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 78, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
    *a4 = 0;
    return 3221225473LL;
  }
}

```

## disassembly

```asm
0x1400229b0  push    rbx
0x1400229b2  push    rbp
0x1400229b3  push    rsi
0x1400229b4  push    rdi
0x1400229b5  push    r14
0x1400229b7  sub     rsp, 30h
0x1400229bb  mov     rbx, [rsp+58h+arg_20]
0x1400229c3  mov     rsi, r9
0x1400229c6  mov     ebp, r8d
0x1400229c9  mov     rdi, rdx
0x1400229cc  mov     r14, rcx
0x1400229cf  mov     rax, [rbx]
0x1400229d2  mov     rax, [rax+20h]
0x1400229d6  test    rax, rax
0x1400229d9  jz      loc_140022A60
0x1400229df  cmp     byte ptr [rax+38h], 0Dh
0x1400229e3  jnz     short loc_140022A3E
0x1400229e5  cmp     byte ptr [rax+39h], 4
0x1400229e9  jnz     short loc_140022A3E
0x1400229eb  mov     rcx, [rax+30h]
0x1400229ef  test    rcx, rcx
0x1400229f2  jz      short loc_140022A3E
0x1400229f4  cmp     dword ptr [rcx+21Ch], 9009Ch
0x1400229fe  jnz     short loc_140022A3E
0x140022a00  cmp     dword ptr [rdx+0Ch], 0C000000Fh
0x140022a07  jnz     short loc_140022A3E
0x140022a09  mov     rcx, cs:WPP_GLOBAL_Control
0x140022a10  lea     rax, WPP_GLOBAL_Control
0x140022a17  cmp     rcx, rax
0x140022a1a  jz      short loc_140022A37
0x140022a1c  cmp     byte ptr [rcx+29h], 4
0x140022a20  jb      short loc_140022A37
0x140022a22  mov     rcx, [rcx+18h]
0x140022a26  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140022a2d  mov     edx, 4Dh ; 'M'
0x140022a32  call    WPP_SF_
0x140022a37  mov     dword ptr [rdi+0Ch], 0C00002F0h
0x140022a3e  mov     r9, rsi
0x140022a41  mov     [rsp+58h+var_38], rbx
0x140022a46  mov     r8d, ebp
0x140022a49  mov     rdx, rdi
0x140022a4c  mov     rcx, r14
0x140022a4f  call    ?OnDeviceIoCompletion@DrDevice@@UEAAJPEAUtagRDPDR_IOCOMPLETION_PACKET@@KPEAHAEAV?$SmartPtr@VDrExchange@@@@@Z; DrDevice::OnDeviceIoCompletion(tagRDPDR_IOCOMPLETION_PACKET *,ulong,int *,SmartPtr<DrExchange> &)
0x140022a54  add     rsp, 30h
0x140022a58  pop     r14
0x140022a5a  pop     rdi
0x140022a5b  pop     rsi
0x140022a5c  pop     rbp
0x140022a5d  pop     rbx
0x140022a5e  retn
0x140022a60  mov     rcx, cs:WPP_GLOBAL_Control
0x140022a67  lea     rax, WPP_GLOBAL_Control
0x140022a6e  cmp     rcx, rax
0x140022a71  jz      short loc_140022A8E
0x140022a73  cmp     byte ptr [rcx+29h], 5
0x140022a77  jb      short loc_140022A8E
0x140022a79  mov     rcx, [rcx+18h]
0x140022a7d  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140022a84  mov     edx, 4Eh ; 'N'
0x140022a89  call    WPP_SF_
0x140022a8e  mov     dword ptr [rsi], 0
0x140022a94  mov     eax, 0C0000001h
0x140022a99  add     rsp, 30h
0x140022a9d  pop     r14
0x140022a9f  pop     rdi
0x140022aa0  pop     rsi
0x140022aa1  pop     rbp
0x140022aa2  pop     rbx
0x140022aa3  retn
```
