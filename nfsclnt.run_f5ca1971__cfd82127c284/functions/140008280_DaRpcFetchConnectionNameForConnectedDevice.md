# DaRpcFetchConnectionNameForConnectedDevice

- ea: `0x140008280`
- end: `0x1400085e1`
- name: `DaRpcFetchConnectionNameForConnectedDevice`
- size: `865`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation`

## callees

- `0x140002bd8`
- `0x140002c00`
- `0x140002c40`
- `0x140002fbc`
- `0x140008280`
- `0x140009b80`
- `0x14000a0b0`
- `0x140018350`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140008434`
- `KERNEL32!EnterCriticalSection` at `0x140008434`
- `KERNEL32!LeaveCriticalSection` at `0x1400084f9`
- `KERNEL32!LeaveCriticalSection` at `0x140008564`
- `KERNEL32!LeaveCriticalSection` at `0x1400084f9`
- `KERNEL32!LeaveCriticalSection` at `0x140008564`
- `msvcrt!_wcsicmp` at `0x14000847e`
- `msvcrt!_wcsicmp` at `0x14000847e`
- `msvcrt!wcscpy_s` at `0x1400084ec`
- `msvcrt!wcscpy_s` at `0x1400084ec`
- `RPCRT4!RpcImpersonateClient` at `0x14000835e`
- `RPCRT4!RpcImpersonateClient` at `0x14000835e`

## pseudocode

```c
__int64 __fastcall DaRpcFetchConnectionNameForConnectedDevice(
        __int64 a1,
        int a2,
        int a3,
        const wchar_t *a4,
        unsigned int SizeInWords,
        wchar_t *Destination,
        unsigned int *a7)
{
  _QWORD *v10; // rcx
  unsigned int v11; // eax
  __int64 v13; // rcx
  void *v14; // rcx
  unsigned int v15; // eax
  unsigned int v16; // ebx
  HGLOBAL v17; // rbx
  __int64 v18; // rax
  const wchar_t *v19; // rcx
  __int64 v20; // rax
  unsigned int v21; // eax
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  struct _LUID DestinationLuid; // [rsp+30h] [rbp-88h] BYREF
  char v25[48]; // [rsp+38h] [rbp-80h] BYREF

  strcpy(v25, "DaRpcFetchConnectionNameForConnectedDevice");
  DestinationLuid = 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids);
    v10 = WPP_GLOBAL_Control;
  }
  if ( !a3 || !SizeInWords || !a4 || !Destination || !a7 )
  {
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 2) != 0 )
      WPP_SF_s(v10[2], 49, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, v25);
    return 87;
  }
  *a7 = 0;
  *Destination = 0;
  v11 = RpcImpersonateClient(0);
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, v11);
    return 5;
  }
  if ( (int)GetLuid(&DestinationLuid) < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids);
    SafeRpcRevertToSelf(v14, 766);
    return 5;
  }
  v15 = SafeRpcRevertToSelf(v13, 770);
  v16 = v15;
  if ( v15 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52,
        (unsigned int)&WPP_4b94345935ba3175354bb878a9e98408_Traceguids,
        (unsigned int)v25,
        v15);
    return v16;
  }
  EnterCriticalSection(&DeviceListCS);
  v17 = pDeviceList;
  if ( !pDeviceList )
  {
LABEL_45:
    v16 = 87;
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v23 = 53;
LABEL_48:
      WPP_SF_(v22[2], v23, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids);
    }
LABEL_49:
    LeaveCriticalSection(&DeviceListCS);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, v16);
    return v16;
  }
  do
  {
    if ( DestinationLuid.LowPart == *(_DWORD *)v17 && DestinationLuid.HighPart == *((_DWORD *)v17 + 1) )
    {
      v18 = *((_QWORD *)v17 + 4);
      if ( a2 )
      {
        if ( !v18 )
          goto LABEL_33;
        v19 = (const wchar_t *)*((_QWORD *)v17 + 4);
      }
      else
      {
        if ( v18 )
          goto LABEL_33;
        v19 = (const wchar_t *)*((_QWORD *)v17 + 5);
        if ( !v19 )
          goto LABEL_33;
      }
      if ( !_wcsicmp(v19, a4) )
        break;
    }
LABEL_33:
    v17 = (HGLOBAL)*((_QWORD *)v17 + 8);
  }
  while ( v17 );
  if ( !v17 )
    goto LABEL_45;
  v20 = -1;
  do
    ++v20;
  while ( *(_WORD *)(*((_QWORD *)v17 + 6) + 2 * v20) );
  v21 = v20 + 1;
  *a7 = v21;
  if ( v21 > SizeInWords )
  {
    v16 = 234;
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v23 = 54;
      goto LABEL_48;
    }
    goto LABEL_49;
  }
  wcscpy_s(Destination, SizeInWords, *((const wchar_t **)v17 + 6));
  LeaveCriticalSection(&DeviceListCS);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x140008280  push    rbx
0x140008282  push    rbp
0x140008283  push    rsi
0x140008284  push    rdi
0x140008285  push    r12
0x140008287  push    r13
0x140008289  push    r14
0x14000828b  push    r15
0x14000828d  sub     rsp, 78h
0x140008291  mov     rax, cs:__security_cookie
0x140008298  xor     rax, rsp
0x14000829b  mov     [rsp+0B8h+var_50], rax
0x1400082a0  movups  xmm0, xmmword ptr cs:aDarpcfetchconn_0; "DaRpcFetchConnectionNameForConnectedDev"...
0x1400082a7  mov     r15, [rsp+0B8h+Destination]
0x1400082af  xor     r12d, r12d
0x1400082b2  movups  xmm1, xmmword ptr cs:aDarpcfetchconn_0+10h; "tionNameForConnectedDevice"
0x1400082b9  mov     r14, [rsp+0B8h+arg_30]
0x1400082c1  mov     rsi, r9
0x1400082c4  movups  xmmword ptr [rsp+0B8h+var_80], xmm0
0x1400082c9  mov     ebx, r8d
0x1400082cc  mov     ebp, edx
0x1400082ce  movups  xmm0, xmmword ptr cs:aDarpcfetchconn_0+1Bh; "ConnectedDevice"
0x1400082d5  mov     qword ptr [rsp+0B8h+DestinationLuid.LowPart], r12
0x1400082da  movups  xmmword ptr [rsp+0B8h+var_80+10h], xmm1
0x1400082df  movups  xmmword ptr [rsp+0B8h+var_80+1Bh], xmm0
0x1400082e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400082eb  lea     rax, WPP_GLOBAL_Control
0x1400082f2  lea     r13, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x1400082f9  cmp     rcx, rax
0x1400082fc  jz      short loc_140008323
0x1400082fe  test    byte ptr [rcx+1Ch], 1
0x140008302  jz      short loc_140008323
0x140008304  mov     rcx, [rcx+10h]
0x140008308  lea     edx, [r12+30h]
0x14000830d  mov     r8, r13
0x140008310  call    WPP_SF_
0x140008315  mov     rcx, cs:WPP_GLOBAL_Control
0x14000831c  lea     rax, WPP_GLOBAL_Control
0x140008323  test    ebx, ebx
0x140008325  jz      loc_14000859D
0x14000832b  mov     edi, dword ptr [rsp+0B8h+SizeInWords]
0x140008332  test    edi, edi
0x140008334  jz      loc_14000859D
0x14000833a  test    rsi, rsi
0x14000833d  jz      loc_14000859D
0x140008343  test    r15, r15
0x140008346  jz      loc_14000859D
0x14000834c  test    r14, r14
0x14000834f  jz      loc_14000859D
0x140008355  mov     [r14], r12d
0x140008358  xor     ecx, ecx; BindingHandle
0x14000835a  mov     [r15], r12w
0x14000835e  call    cs:__imp_RpcImpersonateClient
0x140008364  test    eax, eax
0x140008366  jz      short loc_14000839F
0x140008368  mov     rcx, cs:WPP_GLOBAL_Control
0x14000836f  lea     rdi, WPP_GLOBAL_Control
0x140008376  cmp     rcx, rdi
0x140008379  jz      short loc_140008395
0x14000837b  test    byte ptr [rcx+1Ch], 2
0x14000837f  jz      short loc_140008395
0x140008381  mov     rcx, [rcx+10h]
0x140008385  mov     edx, 32h ; '2'
0x14000838a  mov     r9d, eax
0x14000838d  mov     r8, r13
0x140008390  call    WPP_SF_d
0x140008395  mov     eax, 5
0x14000839a  jmp     loc_1400085C3
0x14000839f  lea     rcx, [rsp+0B8h+DestinationLuid]; DestinationLuid
0x1400083a4  call    GetLuid
0x1400083a9  test    eax, eax
0x1400083ab  jns     short loc_1400083E3
0x1400083ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400083b4  lea     rdi, WPP_GLOBAL_Control
0x1400083bb  cmp     rcx, rdi
0x1400083be  jz      short loc_1400083D7
0x1400083c0  test    byte ptr [rcx+1Ch], 2
0x1400083c4  jz      short loc_1400083D7
0x1400083c6  mov     rcx, [rcx+10h]
0x1400083ca  mov     edx, 33h ; '3'
0x1400083cf  mov     r8, r13
0x1400083d2  call    WPP_SF_
0x1400083d7  mov     edx, 2FEh
0x1400083dc  call    SafeRpcRevertToSelf
0x1400083e1  jmp     short loc_140008395
0x1400083e3  mov     edx, 302h
0x1400083e8  call    SafeRpcRevertToSelf
0x1400083ed  mov     ebx, eax
0x1400083ef  test    eax, eax
0x1400083f1  jz      short loc_14000842D
0x1400083f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400083fa  lea     rdi, WPP_GLOBAL_Control
0x140008401  cmp     rcx, rdi
0x140008404  jz      short loc_140008426
0x140008406  test    byte ptr [rcx+1Ch], 2
0x14000840a  jz      short loc_140008426
0x14000840c  mov     rcx, [rcx+10h]
0x140008410  lea     r9, [rsp+0B8h+var_80]
0x140008415  mov     edx, 34h ; '4'
0x14000841a  mov     [rsp+0B8h+var_98], eax
0x14000841e  mov     r8, r13
0x140008421  call    WPP_SF_sd
0x140008426  mov     eax, ebx
0x140008428  jmp     loc_1400085C3
0x14000842d  lea     rcx, DeviceListCS; lpCriticalSection
0x140008434  call    cs:__imp_EnterCriticalSection
0x14000843a  mov     rbx, cs:pDeviceList
0x140008441  test    rbx, rbx
0x140008444  jz      loc_140008530
0x14000844a  mov     eax, [rbx]
0x14000844c  cmp     [rsp+0B8h+DestinationLuid.LowPart], eax
0x140008450  jnz     short loc_140008488
0x140008452  mov     eax, [rbx+4]
0x140008455  cmp     [rsp+0B8h+DestinationLuid.HighPart], eax
0x140008459  jnz     short loc_140008488
0x14000845b  mov     rax, [rbx+20h]
0x14000845f  test    ebp, ebp
0x140008461  jz      short loc_14000846D
0x140008463  test    rax, rax
0x140008466  jz      short loc_140008488
0x140008468  mov     rcx, rax
0x14000846b  jmp     short loc_14000847B
0x14000846d  test    rax, rax
0x140008470  jnz     short loc_140008488
0x140008472  mov     rcx, [rbx+28h]; String1
0x140008476  test    rcx, rcx
0x140008479  jz      short loc_140008488
0x14000847b  mov     rdx, rsi; String2
0x14000847e  call    cs:__imp__wcsicmp
0x140008484  test    eax, eax
0x140008486  jz      short loc_140008491
0x140008488  mov     rbx, [rbx+40h]
0x14000848c  test    rbx, rbx
0x14000848f  jnz     short loc_14000844A
0x140008491  test    rbx, rbx
0x140008494  jz      loc_140008530
0x14000849a  mov     rcx, [rbx+30h]
0x14000849e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400084a2  inc     rax
0x1400084a5  cmp     [rcx+rax*2], r12w
0x1400084aa  jnz     short loc_1400084A2
0x1400084ac  inc     eax
0x1400084ae  mov     [r14], eax
0x1400084b1  cmp     eax, edi
0x1400084b3  jbe     short loc_1400084E2
0x1400084b5  mov     ebx, 0EAh
0x1400084ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400084c1  lea     rdi, WPP_GLOBAL_Control
0x1400084c8  cmp     rcx, rdi
0x1400084cb  jz      loc_14000855D
0x1400084d1  test    byte ptr [rcx+1Ch], 2
0x1400084d5  jz      loc_14000855D
0x1400084db  mov     edx, 36h ; '6'
0x1400084e0  jmp     short loc_140008551
0x1400084e2  mov     r8, [rbx+30h]; Source
0x1400084e6  mov     rdx, rdi; SizeInWords
0x1400084e9  mov     rcx, r15; Destination
0x1400084ec  call    cs:__imp_wcscpy_s
0x1400084f2  lea     rcx, DeviceListCS; lpCriticalSection
0x1400084f9  call    cs:__imp_LeaveCriticalSection
0x1400084ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140008506  lea     rdi, WPP_GLOBAL_Control
0x14000850d  cmp     rcx, rdi
0x140008510  jz      short loc_140008529
0x140008512  test    byte ptr [rcx+1Ch], 1
0x140008516  jz      short loc_140008529
0x140008518  mov     rcx, [rcx+10h]
0x14000851c  mov     edx, 37h ; '7'
0x140008521  mov     r8, r13
0x140008524  call    WPP_SF_
0x140008529  xor     eax, eax
0x14000852b  jmp     loc_1400085C3
0x140008530  mov     ebx, 57h ; 'W'
0x140008535  mov     rcx, cs:WPP_GLOBAL_Control
0x14000853c  lea     rdi, WPP_GLOBAL_Control
0x140008543  cmp     rcx, rdi
0x140008546  jz      short loc_14000855D
0x140008548  test    byte ptr [rcx+1Ch], 2
0x14000854c  jz      short loc_14000855D
0x14000854e  lea     edx, [rbx-22h]
0x140008551  mov     rcx, [rcx+10h]
0x140008555  mov     r8, r13
0x140008558  call    WPP_SF_
0x14000855d  lea     rcx, DeviceListCS; lpCriticalSection
0x140008564  call    cs:__imp_LeaveCriticalSection
0x14000856a  mov     rcx, cs:WPP_GLOBAL_Control
0x140008571  cmp     rcx, rdi
0x140008574  jz      loc_140008426
0x14000857a  test    byte ptr [rcx+1Ch], 2
0x14000857e  jz      loc_140008426
0x140008584  mov     rcx, [rcx+10h]
0x140008588  mov     edx, 38h ; '8'
0x14000858d  mov     r9d, ebx
0x140008590  mov     r8, r13
0x140008593  call    WPP_SF_d
0x140008598  jmp     loc_140008426
0x14000859d  cmp     rcx, rax
0x1400085a0  jz      short loc_1400085BE
0x1400085a2  test    byte ptr [rcx+1Ch], 2
0x1400085a6  jz      short loc_1400085BE
0x1400085a8  mov     rcx, [rcx+10h]
0x1400085ac  lea     r9, [rsp+0B8h+var_80]
0x1400085b1  mov     edx, 31h ; '1'
0x1400085b6  mov     r8, r13
0x1400085b9  call    WPP_SF_s
0x1400085be  mov     eax, 57h ; 'W'
0x1400085c3  mov     rcx, [rsp+0B8h+var_50]
0x1400085c8  xor     rcx, rsp; StackCookie
0x1400085cb  call    __security_check_cookie
0x1400085d0  add     rsp, 78h
0x1400085d4  pop     r15
0x1400085d6  pop     r14
0x1400085d8  pop     r13
0x1400085da  pop     r12
0x1400085dc  pop     rdi
0x1400085dd  pop     rsi
0x1400085de  pop     rbp
0x1400085df  pop     rbx
0x1400085e0  retn
```
