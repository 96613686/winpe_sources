# CKsClockF::ClockThread(CKsClockF *)

- ea: `0x10034de0`
- end: `0x10034f12`
- name: `?ClockThread@CKsClockF@@CGJPAV1@@Z`
- size: `306`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1001f3b0`
- `0x1002d510`
- `0x10034d89`
- `0x10034de0`
- `0x1003b760`

## import_xrefs

- `KERNEL32!WaitForSingleObjectEx` at `0x10034e7b`
- `KERNEL32!WaitForSingleObjectEx` at `0x10034e7b`

## pseudocode

```c
ULONG __stdcall CKsClockF::ClockThread(char *Parameter)
{
  int v1; // ecx
  volatile signed __int32 *v2; // edi
  __int64 v3; // rax
  CKsClockF *v5; // [esp+0h] [ebp-30h]
  enum KSSTATE v6; // [esp+4h] [ebp-2Ch]
  DWORD BytesReturned; // [esp+Ch] [ebp-24h] BYREF
  __int64 OutBuffer; // [esp+10h] [ebp-20h] BYREF
  GUID InBuffer; // [esp+18h] [ebp-18h] BYREF
  int v10; // [esp+28h] [ebp-8h]
  int v11; // [esp+2Ch] [ebp-4h]

  v1 = *((_DWORD *)Parameter + 9);
  InBuffer = _GUID_df12a4c0_ac17_11cf_a5d6_28db04c10000;
  v10 = 0;
  v11 = 2;
  if ( v1 )
  {
    v2 = (volatile signed __int32 *)(Parameter + 48);
    do
    {
      if ( *v2 )
      {
        (*(void (__thiscall **)(_DWORD, _DWORD, __int64 *))(**((_DWORD **)Parameter + 5) + 12))(
          *(_DWORD *)(**((_DWORD **)Parameter + 5) + 12),
          *((_DWORD *)Parameter + 5),
          &OutBuffer);
        if ( OutBuffer <= *((_QWORD *)Parameter + 5) )
          LODWORD(v3) = 0;
        else
          v3 = (OutBuffer - *((_QWORD *)Parameter + 5)) / 10000;
      }
      else
      {
        LODWORD(v3) = 1000;
        if ( v1 != 2 )
          LODWORD(v3) = -1;
      }
      WaitForSingleObjectEx(*((HANDLE *)Parameter + 7), v3, 0);
      if ( *((_DWORD *)Parameter + 9) == 2 )
      {
        BytesReturned = 0;
        if ( _InterlockedCompareExchange(v2, 0, 1) )
        {
          CKsClockF::SetState(v5, v6);
          if ( *((_DWORD *)Parameter + 9) != 2 )
            CKsClockF::SetState(v5, v6);
        }
        (*(void (__thiscall **)(_DWORD, _DWORD, __int64 *))(**((_DWORD **)Parameter + 5) + 12))(
          *(_DWORD *)(**((_DWORD **)Parameter + 5) + 12),
          *((_DWORD *)Parameter + 5),
          &OutBuffer);
        OutBuffer -= *((_QWORD *)Parameter + 5);
        KsSynchronousDeviceControl(
          *((HANDLE *)Parameter + 8),
          0x2F0003u,
          &InBuffer,
          0x18u,
          &OutBuffer,
          8u,
          &BytesReturned);
      }
      v1 = *((_DWORD *)Parameter + 9);
    }
    while ( v1 );
  }
  return 0;
}

```

## disassembly

```asm
0x10034de0  mov     edi, edi
0x10034de2  push    ebp
0x10034de3  mov     ebp, esp
0x10034de5  and     esp, 0FFFFFFF8h
0x10034de8  sub     esp, 24h
0x10034deb  push    ebx
0x10034dec  mov     ebx, [ebp+Parameter]
0x10034def  push    esi; enum KSSTATE
0x10034df0  push    edi; this
0x10034df1  mov     esi, offset __GUID_df12a4c0_ac17_11cf_a5d6_28db04c10000
0x10034df6  lea     edi, [esp+30h+InBuffer]
0x10034dfa  mov     ecx, [ebx+24h]
0x10034dfd  movsd
0x10034dfe  movsd
0x10034dff  movsd
0x10034e00  movsd
0x10034e01  mov     [esp+30h+var_8], 0
0x10034e09  mov     [esp+30h+var_4], 2
0x10034e11  test    ecx, ecx
0x10034e13  jz      loc_10034F07
0x10034e19  lea     edi, [ebx+30h]
0x10034e1c  cmp     dword ptr [edi], 0
0x10034e1f  jz      short loc_10034E67
0x10034e21  mov     eax, [ebx+14h]
0x10034e24  lea     edx, [esp+30h+OutBuffer]
0x10034e28  push    edx
0x10034e29  push    eax
0x10034e2a  mov     ecx, [eax]
0x10034e2c  mov     esi, [ecx+0Ch]
0x10034e2f  mov     ecx, esi; this
0x10034e31  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10034e37  call    esi
0x10034e39  mov     ecx, dword ptr [esp+30h+OutBuffer+4]
0x10034e3d  cmp     ecx, [ebx+2Ch]
0x10034e40  jl      short loc_10034E63
0x10034e42  mov     eax, dword ptr [esp+30h+OutBuffer]
0x10034e46  jg      short loc_10034E4D
0x10034e48  cmp     eax, [ebx+28h]
0x10034e4b  jbe     short loc_10034E63
0x10034e4d  sub     eax, [ebx+28h]
0x10034e50  push    0
0x10034e52  sbb     ecx, [ebx+2Ch]
0x10034e55  push    2710h
0x10034e5a  push    ecx
0x10034e5b  push    eax
0x10034e5c  call    __alldiv
0x10034e61  jmp     short loc_10034E75
0x10034e63  xor     eax, eax
0x10034e65  jmp     short loc_10034E75
0x10034e67  or      edx, 0FFFFFFFFh
0x10034e6a  mov     eax, 3E8h
0x10034e6f  cmp     ecx, 2
0x10034e72  cmovnz  eax, edx
0x10034e75  push    0; bAlertable
0x10034e77  push    eax; dwMilliseconds
0x10034e78  push    dword ptr [ebx+1Ch]; hHandle
0x10034e7b  call    ds:__imp__WaitForSingleObjectEx@12; WaitForSingleObjectEx(x,x,x)
0x10034e81  cmp     dword ptr [ebx+24h], 2
0x10034e85  jnz     short loc_10034EFC
0x10034e87  xor     eax, eax
0x10034e89  mov     [esp+30h+BytesReturned], 0
0x10034e91  xor     ecx, ecx
0x10034e93  inc     eax
0x10034e94  lock cmpxchg [edi], ecx
0x10034e98  test    eax, eax
0x10034e9a  jz      short loc_10034EB6
0x10034e9c  push    3
0x10034e9e  pop     edx
0x10034e9f  mov     ecx, ebx
0x10034ea1  call    ?SetState@CKsClockF@@AAGJW4KSSTATE@@@Z; CKsClockF::SetState(KSSTATE)
0x10034ea6  cmp     dword ptr [ebx+24h], 2
0x10034eaa  jz      short loc_10034EB6
0x10034eac  push    2
0x10034eae  pop     edx
0x10034eaf  mov     ecx, ebx
0x10034eb1  call    ?SetState@CKsClockF@@AAGJW4KSSTATE@@@Z; CKsClockF::SetState(KSSTATE)
0x10034eb6  mov     eax, [ebx+14h]
0x10034eb9  lea     edx, [esp+30h+OutBuffer]
0x10034ebd  push    edx
0x10034ebe  push    eax
0x10034ebf  mov     ecx, [eax]
0x10034ec1  mov     esi, [ecx+0Ch]
0x10034ec4  mov     ecx, esi; this
0x10034ec6  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10034ecc  call    esi
0x10034ece  mov     eax, [ebx+28h]
0x10034ed1  sub     dword ptr [esp+30h+OutBuffer], eax
0x10034ed5  mov     eax, [ebx+2Ch]
0x10034ed8  sbb     dword ptr [esp+30h+OutBuffer+4], eax
0x10034edc  lea     eax, [esp+30h+BytesReturned]
0x10034ee0  push    eax; lpBytesReturned
0x10034ee1  push    8; nOutBufferSize
0x10034ee3  lea     eax, [esp+38h+OutBuffer]
0x10034ee7  push    eax; lpOutBuffer
0x10034ee8  push    18h; nInBufferSize
0x10034eea  lea     eax, [esp+40h+InBuffer]
0x10034eee  push    eax; lpInBuffer
0x10034eef  push    2F0003h; dwIoControlCode
0x10034ef4  push    dword ptr [ebx+20h]; hDevice
0x10034ef7  call    _KsSynchronousDeviceControl@28; KsSynchronousDeviceControl(x,x,x,x,x,x,x)
0x10034efc  mov     ecx, [ebx+24h]
0x10034eff  test    ecx, ecx
0x10034f01  jnz     loc_10034E1C
0x10034f07  pop     edi
0x10034f08  pop     esi
0x10034f09  xor     eax, eax
0x10034f0b  pop     ebx
0x10034f0c  mov     esp, ebp
0x10034f0e  pop     ebp
0x10034f0f  retn    4
```
