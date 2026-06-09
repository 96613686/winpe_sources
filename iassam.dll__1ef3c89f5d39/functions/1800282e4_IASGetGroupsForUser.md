# IASGetGroupsForUser

- ea: `0x1800282e4`
- end: `0x1800285bf`
- name: `IASGetGroupsForUser`
- size: `731`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000dbc0`

## callees

- `0x180027e8c`
- `0x1800282e4`
- `0x180029b00`
- `0x18002a824`
- `0x18002a878`
- `0x18002addc`
- `0x18002e010`

## import_xrefs

- `ntdll!RtlCopySid` at `0x1800283fa`
- `ntdll!RtlCopySid` at `0x1800283fa`
- `ntdll!RtlLengthSid` at `0x1800283cf`
- `ntdll!RtlLengthSid` at `0x1800283cf`
- `ntdll!RtlFreeHeap` at `0x180028594`
- `ntdll!RtlFreeHeap` at `0x180028594`
- `ntdll!RtlNtStatusToDosError` at `0x180028378`
- `ntdll!RtlNtStatusToDosError` at `0x180028468`
- `ntdll!RtlNtStatusToDosError` at `0x180028378`
- `ntdll!RtlNtStatusToDosError` at `0x180028468`
- `KERNEL32!LocalAlloc` at `0x1800284bf`
- `KERNEL32!LocalAlloc` at `0x1800284bf`
- `KERNEL32!LocalFree` at `0x180028560`
- `KERNEL32!LocalFree` at `0x180028560`
- `SAMLIB!SamQueryInformationUser` at `0x18002836c`
- `SAMLIB!SamQueryInformationUser` at `0x18002836c`
- `SAMLIB!SamGetGroupsForUser` at `0x18002845c`
- `SAMLIB!SamGetGroupsForUser` at `0x18002845c`
- `SAMLIB!SamFreeMemory` at `0x180028404`
- `SAMLIB!SamFreeMemory` at `0x180028571`
- `SAMLIB!SamFreeMemory` at `0x18002857b`
- `SAMLIB!SamFreeMemory` at `0x180028404`
- `SAMLIB!SamFreeMemory` at `0x180028571`
- `SAMLIB!SamFreeMemory` at `0x18002857b`
- `SAMLIB!SamRidToSid` at `0x1800283c1`
- `SAMLIB!SamRidToSid` at `0x1800283c1`
- `SAMLIB!SamCloseHandle` at `0x18002859e`
- `SAMLIB!SamCloseHandle` at `0x18002859e`

## pseudocode

```c
__int64 __fastcall IASGetGroupsForUser(
        __int64 a1,
        wchar_t *a2,
        __int64 (*a3)(void),
        int a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        _QWORD *a8,
        ULONG *a9)
{
  ULONG v10; // ebx
  NTSTATUS v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rdx
  void *v14; // rax
  int v15; // eax
  NTSTATUS GroupsForUser; // eax
  unsigned int v17; // edi
  unsigned int v18; // ecx
  SIZE_T v19; // rdx
  _DWORD *v20; // rsi
  unsigned int v21; // r12d
  char *v22; // r14
  __int64 v23; // r13
  __int64 v24; // rbx
  __int64 v25; // rdi
  unsigned int v27; // [rsp+40h] [rbp-30h] BYREF
  ULONG v28; // [rsp+44h] [rbp-2Ch] BYREF
  __int64 v29; // [rsp+48h] [rbp-28h] BYREF
  PVOID P; // [rsp+50h] [rbp-20h] BYREF
  __int64 v31; // [rsp+58h] [rbp-18h] BYREF
  PSID Sid; // [rsp+60h] [rbp-10h] BYREF
  __int64 v33; // [rsp+68h] [rbp-8h] BYREF
  int v34; // [rsp+B0h] [rbp+40h]

  v34 = (int)a3;
  v31 = 0;
  P = 0;
  v28 = 0;
  v29 = 0;
  v33 = 0;
  v27 = 0;
  Sid = 0;
  v10 = IASSamOpenUser(a2, (__int64)&v28, (__int64)&P, (__int64)&v31);
  if ( !v10 )
  {
    v11 = SamQueryInformationUser(v31, 21, &v29);
    if ( v11 >= 0 )
    {
      v12 = v29;
      if ( (*(_DWORD *)(v29 + 284) & 0x380000) == 0x380000 )
      {
        v13 = v28;
        *a7 = (*(_DWORD *)(v29 + 280) >> 4) & 1;
        if ( (int)SamRidToSid(v31, v13, &Sid) >= 0 )
        {
          *a9 = RtlLengthSid(Sid);
          v14 = (void *)a3();
          *a8 = v14;
          if ( v14 )
            RtlCopySid(*a9, v14, Sid);
          SamFreeMemory(Sid);
        }
        v12 = v29;
        v15 = *(_DWORD *)(v29 + 280);
        if ( (v15 & 1) != 0 )
        {
          v10 = 1331;
        }
        else if ( (v15 & 0x400) != 0 )
        {
          v10 = 1909;
        }
        else
        {
          v10 = IASCheckAccountRestrictions(v29 + 24, v29 + 288, a6);
          if ( !v10 )
          {
            GroupsForUser = SamGetGroupsForUser(v31, &v33, &v27);
            if ( GroupsForUser >= 0 )
            {
              v17 = IASLengthRequiredChildSid(P);
              v18 = v17 + 16;
              if ( v17 + 16 < v17
                || v27 > 0xFFFFFFFF / v18
                || (v10 = 8, v17 >= 0xFFFFFFF8)
                || (v19 = v17 + v27 * v18 + 8, (unsigned int)v19 < v17 + 8) )
              {
                v10 = 534;
              }
              else
              {
                v20 = LocalAlloc(0x40u, v19);
                if ( v20 )
                {
                  v21 = 0;
                  *v20 = v27;
                  v22 = (char *)&v20[4 * v27 + 2];
                  if ( v27 )
                  {
                    v23 = v17;
                    do
                    {
                      v24 = 8LL * v21;
                      IASInitializeChildSid(v22, P, *(_DWORD *)(v24 + v33));
                      v25 = 2LL * v21++;
                      *(_QWORD *)&v20[2 * v25 + 2] = v22;
                      v22 += v23;
                      v20[2 * v25 + 4] = *(_DWORD *)(v24 + v33 + 4);
                    }
                    while ( v21 < v27 );
                  }
                  IASInitializeChildSid(v22, P, v28);
                  v10 = IASGetAliasMembership((_DWORD)v22, (_DWORD)v20, v34, a4, a5);
                  LocalFree(v20);
                }
              }
              SamFreeMemory(v33);
            }
            else
            {
              v10 = RtlNtStatusToDosError(GroupsForUser);
            }
          }
          v12 = v29;
        }
      }
      else
      {
        v10 = 5;
      }
      SamFreeMemory(v12);
    }
    else
    {
      v10 = RtlNtStatusToDosError(v11);
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    SamCloseHandle(v31);
  }
  return v10;
}

```

## disassembly

```asm
0x1800282e4  mov     r11, rsp
0x1800282e7  mov     [r11+8], rbx
0x1800282eb  mov     [r11+10h], rsi
0x1800282ef  mov     [r11+20h], r9
0x1800282f3  mov     [r11+18h], r8
0x1800282f7  push    rbp
0x1800282f8  push    rdi
0x1800282f9  push    r12
0x1800282fb  push    r13
0x1800282fd  push    r14
0x1800282ff  mov     rbp, rsp
0x180028302  sub     rsp, 70h
0x180028306  xor     r13d, r13d
0x180028309  mov     rax, rdx
0x18002830c  lea     rdx, [rbp+var_18]
0x180028310  mov     [rbp+var_18], r13
0x180028314  mov     [r11-68h], rdx
0x180028318  mov     rdi, r8
0x18002831b  lea     rdx, [rbp+P]
0x18002831f  mov     [rbp+P], r13
0x180028323  mov     [r11-70h], rdx
0x180028327  xor     r9d, r9d
0x18002832a  lea     rdx, [rbp+var_2C]
0x18002832e  mov     [rbp+var_2C], r13d
0x180028332  mov     [r11-78h], rdx
0x180028336  mov     r8d, 118h
0x18002833c  mov     rdx, rcx
0x18002833f  mov     [rbp+var_28], r13
0x180028343  mov     rcx, rax; Source
0x180028346  mov     [rbp+var_8], r13
0x18002834a  mov     [rbp+var_30], r13d
0x18002834e  mov     [rbp+Sid], r13
0x180028352  call    IASSamOpenUser
0x180028357  mov     ebx, eax
0x180028359  test    eax, eax
0x18002835b  jnz     loc_1800285A4
0x180028361  mov     rcx, [rbp+var_18]
0x180028365  lea     r8, [rbp+var_28]
0x180028369  lea     edx, [rax+15h]
0x18002836c  call    cs:__imp_SamQueryInformationUser
0x180028372  test    eax, eax
0x180028374  jns     short loc_180028385
0x180028376  mov     ecx, eax; Status
0x180028378  call    cs:__imp_RtlNtStatusToDosError
0x18002837e  mov     ebx, eax
0x180028380  jmp     loc_180028581
0x180028385  mov     rcx, [rbp+var_28]
0x180028389  mov     edx, 380000h
0x18002838e  mov     eax, [rcx+11Ch]
0x180028394  and     eax, edx
0x180028396  cmp     eax, edx
0x180028398  jz      short loc_1800283A4
0x18002839a  mov     ebx, 5
0x18002839f  jmp     loc_18002857B
0x1800283a4  mov     ecx, [rcx+118h]
0x1800283aa  lea     r8, [rbp+Sid]
0x1800283ae  mov     rax, [rbp+arg_30]
0x1800283b2  mov     edx, [rbp+var_2C]
0x1800283b5  shr     ecx, 4
0x1800283b8  and     ecx, 1
0x1800283bb  mov     [rax], ecx
0x1800283bd  mov     rcx, [rbp+var_18]
0x1800283c1  call    cs:__imp_SamRidToSid
0x1800283c7  test    eax, eax
0x1800283c9  js      short loc_18002840A
0x1800283cb  mov     rcx, [rbp+Sid]; Sid
0x1800283cf  call    cs:__imp_RtlLengthSid
0x1800283d5  mov     rbx, [rbp+arg_40]
0x1800283d9  mov     ecx, eax
0x1800283db  mov     rax, rdi
0x1800283de  mov     [rbx], ecx
0x1800283e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283e5  mov     rdx, [rbp+arg_38]
0x1800283e9  mov     [rdx], rax
0x1800283ec  test    rax, rax
0x1800283ef  jz      short loc_180028400
0x1800283f1  mov     r8, [rbp+Sid]; SourceSid
0x1800283f5  mov     rdx, rax; DestinationSid
0x1800283f8  mov     ecx, [rbx]; DestinationSidLength
0x1800283fa  call    cs:__imp_RtlCopySid
0x180028400  mov     rcx, [rbp+Sid]
0x180028404  call    cs:__imp_SamFreeMemory
0x18002840a  mov     rcx, [rbp+var_28]
0x18002840e  mov     eax, [rcx+118h]
0x180028414  test    al, 1
0x180028416  jz      short loc_180028422
0x180028418  mov     ebx, 533h
0x18002841d  jmp     loc_18002857B
0x180028422  bt      eax, 0Ah
0x180028426  jnb     short loc_180028432
0x180028428  mov     ebx, 775h
0x18002842d  jmp     loc_18002857B
0x180028432  mov     r8, [rbp+arg_28]
0x180028436  lea     rdx, [rcx+120h]
0x18002843d  add     rcx, 18h
0x180028441  call    IASCheckAccountRestrictions
0x180028446  mov     ebx, eax
0x180028448  test    eax, eax
0x18002844a  jnz     loc_180028577
0x180028450  mov     rcx, [rbp+var_18]
0x180028454  lea     r8, [rbp+var_30]
0x180028458  lea     rdx, [rbp+var_8]
0x18002845c  call    cs:__imp_SamGetGroupsForUser
0x180028462  test    eax, eax
0x180028464  jns     short loc_180028475
0x180028466  mov     ecx, eax; Status
0x180028468  call    cs:__imp_RtlNtStatusToDosError
0x18002846e  mov     ebx, eax
0x180028470  jmp     loc_180028577
0x180028475  mov     rcx, [rbp+P]
0x180028479  call    IASLengthRequiredChildSid
0x18002847e  mov     edi, eax
0x180028480  lea     ecx, [rdi+10h]
0x180028483  cmp     ecx, eax
0x180028485  jb      loc_180028568
0x18002848b  xor     edx, edx
0x18002848d  or      eax, 0FFFFFFFFh
0x180028490  div     ecx
0x180028492  cmp     [rbp+var_30], eax
0x180028495  ja      loc_180028568
0x18002849b  lea     eax, [rdi+8]
0x18002849e  mov     ebx, 8
0x1800284a3  cmp     eax, ebx
0x1800284a5  jb      loc_180028568
0x1800284ab  imul    ecx, [rbp+var_30]
0x1800284af  lea     edx, [rcx+8]
0x1800284b2  add     edx, edi; uBytes
0x1800284b4  cmp     edx, eax
0x1800284b6  jb      loc_180028568
0x1800284bc  lea     ecx, [rbx+38h]; uFlags
0x1800284bf  call    cs:__imp_LocalAlloc
0x1800284c5  mov     rsi, rax
0x1800284c8  test    rax, rax
0x1800284cb  jz      loc_18002856D
0x1800284d1  mov     eax, [rbp+var_30]
0x1800284d4  mov     r12d, r13d
0x1800284d7  mov     [rsi], eax
0x1800284d9  mov     ecx, [rbp+var_30]
0x1800284dc  mov     r14d, ecx
0x1800284df  shl     r14, 4
0x1800284e3  add     r14, rbx
0x1800284e6  add     r14, rsi
0x1800284e9  test    ecx, ecx
0x1800284eb  jz      short loc_18002852F
0x1800284ed  mov     r13d, edi
0x1800284f0  mov     r8, [rbp+var_8]
0x1800284f4  mov     rcx, r14; Sid
0x1800284f7  mov     rdx, [rbp+P]; SourceSid
0x1800284fb  mov     edi, r12d
0x1800284fe  lea     rbx, ds:0[rdi*8]
0x180028506  mov     r8d, [rbx+r8]
0x18002850a  call    IASInitializeChildSid
0x18002850f  add     rdi, rdi
0x180028512  inc     r12d
0x180028515  mov     [rsi+rdi*8+8], r14
0x18002851a  add     r14, r13
0x18002851d  mov     rax, [rbp+var_8]
0x180028521  mov     ecx, [rbx+rax+4]
0x180028525  mov     [rsi+rdi*8+10h], ecx
0x180028529  cmp     r12d, [rbp+var_30]
0x18002852d  jb      short loc_1800284F0
0x18002852f  mov     r8d, [rbp+var_2C]
0x180028533  mov     rcx, r14; Sid
0x180028536  mov     rdx, [rbp+P]; SourceSid
0x18002853a  call    IASInitializeChildSid
0x18002853f  mov     rax, [rbp+arg_20]
0x180028543  mov     rdx, rsi
0x180028546  mov     r9, [rbp+arg_18]
0x18002854a  mov     rcx, r14
0x18002854d  mov     r8, [rbp+arg_10]
0x180028551  mov     [rsp+70h+var_50], rax
0x180028556  call    IASGetAliasMembership
0x18002855b  mov     rcx, rsi; hMem
0x18002855e  mov     ebx, eax
0x180028560  call    cs:__imp_LocalFree
0x180028566  jmp     short loc_18002856D
0x180028568  mov     ebx, 216h
0x18002856d  mov     rcx, [rbp+var_8]
0x180028571  call    cs:__imp_SamFreeMemory
0x180028577  mov     rcx, [rbp+var_28]
0x18002857b  call    cs:__imp_SamFreeMemory
0x180028581  mov     rcx, gs:60h
0x18002858a  xor     edx, edx; Flags
0x18002858c  mov     r8, [rbp+P]; P
0x180028590  mov     rcx, [rcx+30h]; HeapHandle
0x180028594  call    cs:__imp_RtlFreeHeap
0x18002859a  mov     rcx, [rbp+var_18]
0x18002859e  call    cs:__imp_SamCloseHandle
0x1800285a4  lea     r11, [rsp+70h+var_s0]
0x1800285a9  mov     eax, ebx
0x1800285ab  mov     rbx, [r11+30h]
0x1800285af  mov     rsi, [r11+38h]
0x1800285b3  mov     rsp, r11
0x1800285b6  pop     r14
0x1800285b8  pop     r13
0x1800285ba  pop     r12
0x1800285bc  pop     rdi
0x1800285bd  pop     rbp
0x1800285be  retn
```
