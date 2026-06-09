# Dhcpv6RenewThread

- ea: `0x1800097f0`
- end: `0x180009976`
- name: `Dhcpv6RenewThread`
- size: `390`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1800097f0`
- `0x18000997c`
- `0x18000bb2c`
- `0x1800337d0`
- `0x1800338c0`
- `0x180033a9c`
- `0x180033b14`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800098c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800098c2`

## pseudocode

```c
__int64 __fastcall Dhcpv6RenewThread(char *Parameter, _QWORD *a2, int a3)
{
  __int64 *v4; // rsi
  unsigned int v5; // edi
  char v7; // al
  int v8; // r15d
  signed __int32 v9; // r14d

  v4 = (__int64 *)(Parameter + 56);
  v5 = 0;
  while ( !**(_DWORD **)&pDhcpv6GlobalIsShuttingDown )
  {
    v5 = LockDhcpContextEx(Parameter);
    v7 = xmmword_1800423E0;
    if ( (xmmword_1800423E0 & 0x10) != 0 )
    {
      v4 = (__int64 *)(Parameter + 56);
      WPP_SF_S(1028, 80, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, *((_QWORD *)Parameter + 7));
      v7 = xmmword_1800423E0;
    }
    if ( v5 )
    {
      if ( (v7 & 2) != 0 )
        WPP_SF_D(1025, 81, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, v5);
      break;
    }
    v8 = *((_DWORD *)Parameter + 149);
    if ( (v7 & 2) != 0 )
      WPP_SF_Sd(1025, 82, a3, *v4, *((_DWORD *)Parameter + 149));
    if ( *((int *)Parameter + 4) > 1 )
    {
      v5 = (*((__int64 (__fastcall **)(char *))Parameter + 72))(Parameter);
      if ( v5 )
      {
        if ( (xmmword_1800423E0 & 2) != 0 )
          WPP_SF_DS(1025, 83, (unsigned int)WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, v5, *v4);
        v5 = 0;
      }
    }
    v9 = _InterlockedExchangeAdd((volatile signed __int32 *)Parameter + 149, -v8);
    ReleaseSemaphore(*((HANDLE *)Parameter + 73), 1, 0);
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_S(1028, 84, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, *v4);
    else
      v4 = (__int64 *)(Parameter + 56);
    if ( v9 == v8 )
      break;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)Parameter + 4, 0xFFFFFFFF) == 1 )
    Dhcpv6DestroyContextEx((__int64)Parameter, a2, a3);
  return v5;
}

```

## disassembly

```asm
0x1800097f0  push    rbx
0x1800097f2  push    rsi
0x1800097f3  push    rdi
0x1800097f4  push    r14
0x1800097f6  push    r15
0x1800097f8  sub     rsp, 30h
0x1800097fc  mov     rbx, rcx
0x1800097ff  lea     rsi, [rcx+38h]
0x180009803  xor     edi, edi
0x180009805  mov     rax, cs:pDhcpv6GlobalIsShuttingDown
0x18000980c  cmp     dword ptr [rax], 0
0x18000980f  jz      short loc_180009831
0x180009811  or      eax, 0FFFFFFFFh
0x180009814  lock xadd [rbx+10h], eax
0x180009819  cmp     eax, 1
0x18000981c  jz      loc_180009969
0x180009822  mov     eax, edi
0x180009824  add     rsp, 30h
0x180009828  pop     r15
0x18000982a  pop     r14
0x18000982c  pop     rdi
0x18000982d  pop     rsi
0x18000982e  pop     rbx
0x18000982f  retn
0x180009831  mov     rcx, rbx
0x180009834  call    LockDhcpContextEx
0x180009839  mov     edi, eax
0x18000983b  mov     al, byte ptr cs:xmmword_1800423E0
0x180009841  test    al, 10h
0x180009843  jz      short loc_180009868
0x180009845  lea     rsi, [rbx+38h]
0x180009849  mov     edx, 50h ; 'P'
0x18000984e  mov     r9, [rsi]
0x180009851  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x180009858  mov     ecx, 404h
0x18000985d  call    WPP_SF_S
0x180009862  mov     al, byte ptr cs:xmmword_1800423E0
0x180009868  test    edi, edi
0x18000986a  jnz     loc_180009943
0x180009870  mov     r15d, [rbx+254h]
0x180009877  test    al, 2
0x180009879  jnz     loc_18000990C
0x18000987f  cmp     dword ptr [rbx+10h], 1
0x180009883  jle     short loc_1800098A5
0x180009885  mov     rax, [rbx+240h]
0x18000988c  mov     rcx, rbx
0x18000988f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009894  mov     edi, eax
0x180009896  test    eax, eax
0x180009898  jz      short loc_1800098A5
0x18000989a  test    byte ptr cs:xmmword_1800423E0, 2
0x1800098a1  jnz     short loc_1800098E9
0x1800098a3  xor     edi, edi
0x1800098a5  mov     r14d, r15d
0x1800098a8  neg     r14d
0x1800098ab  lock xadd [rbx+254h], r14d
0x1800098b4  mov     rcx, [rbx+248h]; hSemaphore
0x1800098bb  xor     r8d, r8d; lpPreviousCount
0x1800098be  lea     edx, [r8+1]; lReleaseCount
0x1800098c2  call    cs:__imp_ReleaseSemaphore
0x1800098c9  nop     dword ptr [rax+rax+00h]
0x1800098ce  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800098d5  jnz     short loc_180009928
0x1800098d7  lea     rsi, [rbx+38h]
0x1800098db  cmp     r14d, r15d
0x1800098de  jnz     loc_180009805
0x1800098e4  jmp     loc_180009811
0x1800098e9  mov     rax, [rsi]
0x1800098ec  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x1800098f3  mov     edx, 53h ; 'S'
0x1800098f8  mov     [rsp+58h+var_38], rax
0x1800098fd  mov     ecx, 401h
0x180009902  mov     r9d, edi
0x180009905  call    WPP_SF_DS
0x18000990a  jmp     short loc_1800098A3
0x18000990c  mov     r9, [rsi]
0x18000990f  mov     edx, 52h ; 'R'
0x180009914  mov     ecx, 401h
0x180009919  mov     dword ptr [rsp+58h+var_38], r15d
0x18000991e  call    WPP_SF_Sd
0x180009923  jmp     loc_18000987F
0x180009928  mov     r9, [rsi]
0x18000992b  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x180009932  mov     edx, 54h ; 'T'
0x180009937  mov     ecx, 404h
0x18000993c  call    WPP_SF_S
0x180009941  jmp     short loc_1800098DB
0x180009943  test    al, 2
0x180009945  jz      loc_180009811
0x18000994b  mov     edx, 51h ; 'Q'
0x180009950  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x180009957  mov     ecx, 401h
0x18000995c  mov     r9d, edi
0x18000995f  call    WPP_SF_D
0x180009964  jmp     loc_180009811
0x180009969  mov     rcx, rbx
0x18000996c  call    Dhcpv6DestroyContextEx
0x180009971  jmp     loc_180009822
```
