# CDetectionAndSharing::DoTurnOn(HWND__ *,NET_FW_PROFILE_TYPE2_ *,_DtshType,int)

- ea: `0x180002b64`
- end: `0x180002d39`
- name: `?DoTurnOn@CDetectionAndSharing@@AEAAJPEAUHWND__@@PEAW4NET_FW_PROFILE_TYPE2_@@W4_DtshType@@H@Z`
- size: `469`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int *, unsigned int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x180003aa0`
- `0x180003ac0`

## callees

- `0x1800025a0`
- `0x180002b64`
- `0x180002e2c`
- `0x180002f84`
- `0x180003128`
- `0x180003410`
- `0x180003570`
- `0x18000388c`
- `0x180003b00`
- `0x180005010`

## pseudocode

```c
__int64 __fastcall CDetectionAndSharing::DoTurnOn(__int64 a1, __int64 a2, unsigned int *a3, unsigned int a4, int a5)
{
  int v5; // r15d
  unsigned int v9; // eax
  int FWServiceInfo; // ebx
  int v11; // r12d
  int v12; // eax
  unsigned int v13; // esi
  unsigned int i; // esi
  __int64 v15; // rax
  __int64 v16; // rdx
  int v18; // [rsp+30h] [rbp-10h] BYREF
  int v19[3]; // [rsp+34h] [rbp-Ch] BYREF
  unsigned int v21; // [rsp+90h] [rbp+50h] BYREF

  v5 = 0;
  if ( a3 )
    v9 = *a3;
  else
    v9 = 0;
  v21 = v9;
  FWServiceInfo = CDetectionAndSharing::InitializeServiceStatusArray((CDetectionAndSharing *)a1);
  if ( FWServiceInfo < 0 )
    return (unsigned int)FWServiceInfo;
  v18 = 0;
  v19[0] = 0;
  FWServiceInfo = CDetectionAndSharing::GetFWServiceInfo((CDetectionAndSharing *)a1, &v18, v19);
  if ( FWServiceInfo < 0 )
    return (unsigned int)FWServiceInfo;
  v11 = a5;
  if ( v19[0] )
    goto LABEL_7;
  if ( a5 )
  {
    v12 = v18;
    goto LABEL_14;
  }
  if ( v18 )
    goto LABEL_15;
  if ( !(unsigned int)IsThirdPartyFwRunning() )
  {
    FWServiceInfo = CDetectionAndSharing::StartServiceW((CDetectionAndSharing *)a1, L"mpssvc");
    if ( FWServiceInfo < 0 )
      return (unsigned int)FWServiceInfo;
    v12 = 1;
LABEL_14:
    if ( v12 )
    {
LABEL_15:
      FWServiceInfo = CDetectionAndSharing::GetFwPolicy((CDetectionAndSharing *)a1);
      if ( FWServiceInfo < 0 )
        return (unsigned int)FWServiceInfo;
      if ( !v21 )
      {
        FWServiceInfo = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(a1 + 72) + 56LL))(
                          *(_QWORD *)(a1 + 72),
                          &v21);
        if ( FWServiceInfo < 0 )
          return (unsigned int)FWServiceInfo;
      }
      if ( !a3 || !*a3 )
        v5 = 1;
      v13 = 0;
      while ( v13 < 3 )
      {
        if ( (dword_180007130[v13] & v21) != 0 )
        {
          FWServiceInfo = CDetectionAndSharing::_TurnOnOrOff(a1, a2, dword_180007130[v13] & v21, a4, v11, v5);
          if ( FWServiceInfo < 0 )
            return (unsigned int)FWServiceInfo;
          ++v13;
        }
        else
        {
          ++v13;
        }
      }
      goto LABEL_27;
    }
  }
LABEL_7:
  FWServiceInfo = 0;
LABEL_27:
  if ( v11 )
  {
    FWServiceInfo = CDetectionAndSharing::GetWindowsServicesStatus((CDetectionAndSharing *)a1);
    if ( FWServiceInfo < 0 )
      return (unsigned int)FWServiceInfo;
    for ( i = 0; (unsigned __int64)i < *(_QWORD *)(a1 + 88); ++i )
    {
      if ( (unsigned __int64)i >= *(_QWORD *)(a1 + 88) )
        ATL::AtlThrowImpl(-2147024809);
      v15 = *(_QWORD *)(a1 + 80);
      v16 = 32LL * i;
      if ( (*(_DWORD *)(v16 + v15 + 16) == a4 || a4 == 4 || a4 == 3 && *(_DWORD *)(v16 + v15 + 16) <= 1u)
        && !*(_DWORD *)(v16 + v15 + 24) )
      {
        CDetectionAndSharing::StartServiceW((CDetectionAndSharing *)a1, *(const unsigned __int16 **)(v16 + v15));
      }
    }
  }
  if ( a3 )
    *a3 = v21;
  return (unsigned int)FWServiceInfo;
}

```

## disassembly

```asm
0x180002b64  mov     [rsp-38h+arg_0], rbx
0x180002b69  mov     [rsp-38h+arg_8], rdx
0x180002b6e  push    rbp
0x180002b6f  push    rsi
0x180002b70  push    rdi
0x180002b71  push    r12
0x180002b73  push    r13
0x180002b75  push    r14
0x180002b77  push    r15
0x180002b79  mov     rbp, rsp
0x180002b7c  sub     rsp, 40h
0x180002b80  xor     r15d, r15d
0x180002b83  mov     r13d, r9d
0x180002b86  mov     r14, r8
0x180002b89  mov     rdi, rcx
0x180002b8c  test    r8, r8
0x180002b8f  jz      short loc_180002B96
0x180002b91  mov     eax, [r8]
0x180002b94  jmp     short loc_180002B99
0x180002b96  mov     eax, r15d
0x180002b99  mov     [rbp+arg_10], eax
0x180002b9c  call    ?InitializeServiceStatusArray@CDetectionAndSharing@@AEAAJXZ; CDetectionAndSharing::InitializeServiceStatusArray(void)
0x180002ba1  mov     ebx, eax
0x180002ba3  test    eax, eax
0x180002ba5  js      loc_180002D14
0x180002bab  lea     r8, [rbp+var_C]; int *
0x180002baf  mov     [rbp+var_10], r15d
0x180002bb3  lea     rdx, [rbp+var_10]; int *
0x180002bb7  mov     [rbp+var_C], r15d
0x180002bbb  mov     rcx, rdi; this
0x180002bbe  call    ?GetFWServiceInfo@CDetectionAndSharing@@AEAAJPEAH0@Z; CDetectionAndSharing::GetFWServiceInfo(int *,int *)
0x180002bc3  mov     ebx, eax
0x180002bc5  test    eax, eax
0x180002bc7  js      loc_180002D14
0x180002bcd  mov     esi, 1
0x180002bd2  mov     r12d, [rbp+arg_20]
0x180002bd6  cmp     [rbp+var_C], r15d
0x180002bda  jz      short loc_180002BE4
0x180002bdc  mov     ebx, r15d
0x180002bdf  jmp     loc_180002CA6
0x180002be4  test    r12d, r12d
0x180002be7  jnz     short loc_180002C15
0x180002be9  cmp     [rbp+var_10], r15d
0x180002bed  jnz     short loc_180002C1C
0x180002bef  call    ?IsThirdPartyFwRunning@@YAHXZ; IsThirdPartyFwRunning(void)
0x180002bf4  test    eax, eax
0x180002bf6  jnz     short loc_180002BDC
0x180002bf8  lea     rdx, aMpssvc; "mpssvc"
0x180002bff  mov     rcx, rdi; this
0x180002c02  call    ?StartServiceW@CDetectionAndSharing@@AEAAJPEBG@Z; CDetectionAndSharing::StartServiceW(ushort const *)
0x180002c07  mov     ebx, eax
0x180002c09  test    eax, eax
0x180002c0b  js      loc_180002D14
0x180002c11  mov     eax, esi
0x180002c13  jmp     short loc_180002C18
0x180002c15  mov     eax, [rbp+var_10]
0x180002c18  test    eax, eax
0x180002c1a  jz      short loc_180002BDC
0x180002c1c  mov     rcx, rdi; this
0x180002c1f  call    ?GetFwPolicy@CDetectionAndSharing@@AEAAJXZ; CDetectionAndSharing::GetFwPolicy(void)
0x180002c24  mov     ebx, eax
0x180002c26  test    eax, eax
0x180002c28  js      loc_180002D14
0x180002c2e  cmp     [rbp+arg_10], r15d
0x180002c32  jnz     short loc_180002C52
0x180002c34  mov     rcx, [rdi+48h]
0x180002c38  lea     rdx, [rbp+arg_10]
0x180002c3c  mov     rax, [rcx]
0x180002c3f  mov     rax, [rax+38h]
0x180002c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c48  mov     ebx, eax
0x180002c4a  test    eax, eax
0x180002c4c  js      loc_180002D14
0x180002c52  test    r14, r14
0x180002c55  jz      short loc_180002C5C
0x180002c57  cmp     [r14], r15d
0x180002c5a  jnz     short loc_180002C5F
0x180002c5c  mov     r15d, esi
0x180002c5f  xor     esi, esi
0x180002c61  cmp     esi, 3
0x180002c64  jnb     short loc_180002CA3
0x180002c66  mov     r8d, [rbp+arg_10]
0x180002c6a  lea     rcx, dword_180007130
0x180002c71  movsxd  rax, esi
0x180002c74  and     r8d, [rcx+rax*4]
0x180002c78  jz      short loc_180002C9D
0x180002c7a  mov     rdx, [rbp+arg_8]
0x180002c7e  mov     r9d, r13d
0x180002c81  mov     [rsp+40h+var_18], r15d
0x180002c86  mov     rcx, rdi
0x180002c89  mov     [rsp+40h+var_20], r12d
0x180002c8e  call    ?_TurnOnOrOff@CDetectionAndSharing@@AEAAJPEAUHWND__@@W4NET_FW_PROFILE_TYPE2_@@W4_DtshType@@HH@Z; CDetectionAndSharing::_TurnOnOrOff(HWND__ *,NET_FW_PROFILE_TYPE2_,_DtshType,int,int)
0x180002c93  mov     ebx, eax
0x180002c95  test    eax, eax
0x180002c97  js      short loc_180002D14
0x180002c99  inc     esi
0x180002c9b  jmp     short loc_180002C61
0x180002c9d  inc     esi
0x180002c9f  test    ebx, ebx
0x180002ca1  jns     short loc_180002C61
0x180002ca3  xor     r15d, r15d
0x180002ca6  test    r12d, r12d
0x180002ca9  jz      short loc_180002D09
0x180002cab  mov     rcx, rdi; this
0x180002cae  call    ?GetWindowsServicesStatus@CDetectionAndSharing@@AEAAJXZ; CDetectionAndSharing::GetWindowsServicesStatus(void)
0x180002cb3  mov     ebx, eax
0x180002cb5  test    eax, eax
0x180002cb7  js      short loc_180002D14
0x180002cb9  mov     esi, r15d
0x180002cbc  cmp     [rdi+58h], r15
0x180002cc0  jbe     short loc_180002D09
0x180002cc2  mov     edx, esi
0x180002cc4  cmp     rdx, [rdi+58h]
0x180002cc8  jnb     short loc_180002D2E
0x180002cca  mov     rax, [rdi+50h]
0x180002cce  shl     rdx, 5
0x180002cd2  cmp     [rdx+rax+10h], r13d
0x180002cd7  jz      short loc_180002CEC
0x180002cd9  cmp     r13d, 4
0x180002cdd  jz      short loc_180002CEC
0x180002cdf  cmp     r13d, 3
0x180002ce3  jnz     short loc_180002CFF
0x180002ce5  cmp     dword ptr [rdx+rax+10h], 1
0x180002cea  ja      short loc_180002CFF
0x180002cec  cmp     [rdx+rax+18h], r15d
0x180002cf1  jnz     short loc_180002CFF
0x180002cf3  mov     rdx, [rdx+rax]; unsigned __int16 *
0x180002cf7  mov     rcx, rdi; this
0x180002cfa  call    ?StartServiceW@CDetectionAndSharing@@AEAAJPEBG@Z; CDetectionAndSharing::StartServiceW(ushort const *)
0x180002cff  inc     esi
0x180002d01  mov     eax, esi
0x180002d03  cmp     rax, [rdi+58h]
0x180002d07  jb      short loc_180002CC2
0x180002d09  test    r14, r14
0x180002d0c  jz      short loc_180002D14
0x180002d0e  mov     eax, [rbp+arg_10]
0x180002d11  mov     [r14], eax
0x180002d14  mov     eax, ebx
0x180002d16  mov     rbx, [rsp+40h+arg_0]
0x180002d1e  add     rsp, 40h
0x180002d22  pop     r15
0x180002d24  pop     r14
0x180002d26  pop     r13
0x180002d28  pop     r12
0x180002d2a  pop     rdi
0x180002d2b  pop     rsi
0x180002d2c  pop     rbp
0x180002d2d  retn
0x180002d2e  mov     ecx, 80070057h; int
0x180002d33  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
