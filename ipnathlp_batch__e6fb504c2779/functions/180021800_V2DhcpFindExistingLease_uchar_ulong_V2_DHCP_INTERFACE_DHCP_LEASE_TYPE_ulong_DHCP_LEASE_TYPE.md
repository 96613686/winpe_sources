# V2DhcpFindExistingLease(uchar *,ulong,_V2_DHCP_INTERFACE *,DHCP_LEASE_TYPE,ulong *,DHCP_LEASE_TYPE *)

- ea: `0x180021800`
- end: `0x180021b37`
- name: `?V2DhcpFindExistingLease@@YAEPEAEKPEAU_V2_DHCP_INTERFACE@@W4DHCP_LEASE_TYPE@@PEAKPEAW42@@Z`
- size: `823`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004d200`
- `0x18008cad8`

## callees

- `0x18000674c`
- `0x18000ca20`
- `0x180021800`
- `0x18004561c`
- `0x1800640c4`
- `0x180064108`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021881`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021881`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021958`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021958`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180021995`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180021995`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800219c2`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800219c2`

## pseudocode

```c
char __fastcall V2DhcpFindExistingLease(const void *a1, unsigned int a2, __int64 a3, __int64 a4, int *a5, _DWORD *a6)
{
  PVOID *v9; // rcx
  int *v10; // r15
  struct _RTL_CRITICAL_SECTION *v11; // rbx
  char v12; // r14
  int v13; // eax
  __int64 v14; // r12
  __int64 v15; // rsi
  unsigned int v16; // ebx
  __int64 v17; // rbp
  __int64 v18; // r9
  ULONGLONG v20; // rdi
  int v21; // edx
  int v22; // [rsp+40h] [rbp-58h]
  int v23; // [rsp+44h] [rbp-54h]
  int v26; // [rsp+B8h] [rbp+20h]

  v26 = a4;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_75f098ceb717321f6a7e914f13ba0684_Traceguids, a4);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 && a2 && a3 )
  {
    v10 = a5;
    if ( a5 )
    {
      v11 = (struct _RTL_CRITICAL_SECTION *)(a3 + 16);
      *a5 = 0;
      v12 = 0;
      EnterCriticalSection((LPCRITICAL_SECTION)(a3 + 16));
      v13 = *(_DWORD *)(a3 + 124);
      if ( v13 >= 0 && (v13 & 0x60000000) == 0x60000000 )
      {
        v14 = 0;
        v22 = 0;
        if ( *(_DWORD *)(a3 + 128) )
        {
          do
          {
            if ( v12 )
              break;
            v15 = 80 * v14 + *(_QWORD *)(a3 + 144);
            if ( *(_QWORD *)(v15 + 72) )
            {
              v16 = 0;
              v23 = *(_DWORD *)v15;
              if ( *(_DWORD *)(v15 + 64) )
              {
                do
                {
                  if ( v12 )
                    break;
                  v17 = *(_QWORD *)(v15 + 72) + 136LL * v16;
                  if ( *(_BYTE *)(v17 + 36) )
                  {
                    if ( *(_BYTE *)(v17 + 37) )
                    {
                      v20 = *(_QWORD *)(v17 + 48) + *(_QWORD *)(v17 + 56);
                      if ( v20 >= GetTickCount64()
                        && a2 == *(_DWORD *)(v17 + 32)
                        && a2 == RtlCompareMemory(a1, (const void *)v17, a2)
                        && (v26 == 3 || *(_DWORD *)(v17 + 40) == v26) )
                      {
                        v21 = v23 & *(_DWORD *)(*(_QWORD *)(a3 + 144) + 80 * v14 + 4)
                            | (v16 << *(_DWORD *)(*(_QWORD *)(a3 + 144) + 80 * v14 + 60));
                        *a5 = v21;
                        if ( a6 )
                          *a6 = *(_DWORD *)(v17 + 40);
                        v12 = 1;
                        V2DhcpTraceLease(
                          "V2DhcpFindExistingLease found existing",
                          v21,
                          (const struct _DYNAMIC_ADDRESS *)v17);
                      }
                    }
                  }
                  ++v16;
                }
                while ( v16 < *(_DWORD *)(v15 + 64) );
                LODWORD(v14) = v22;
              }
            }
            v14 = (unsigned int)(v14 + 1);
            v22 = v14;
          }
          while ( (unsigned int)v14 < *(_DWORD *)(a3 + 128) );
          v11 = (struct _RTL_CRITICAL_SECTION *)(a3 + 16);
        }
      }
      LeaveCriticalSection(v11);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        LOBYTE(v18) = v12 != 0;
        WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_75f098ceb717321f6a7e914f13ba0684_Traceguids, v18);
      }
      return v12;
    }
  }
  else
  {
    v10 = a5;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 2) != 0 && *((_BYTE *)v9 + 25) >= 4u )
  {
    WPP_SF_qDqq(v9[2], 67, WPP_75f098ceb717321f6a7e914f13ba0684_Traceguids, a1, a2, a3, v10);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 )
  {
    *v10 = 0;
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 2) != 0 && *((_BYTE *)v9 + 25) >= 6u )
    WPP_SF_(v9[2], 68, WPP_75f098ceb717321f6a7e914f13ba0684_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x180021800  mov     [rsp+arg_18], r9d
0x180021805  mov     dword ptr [rsp+Length], edx
0x180021809  mov     [rsp+Source1], rcx
0x18002180e  push    rbx
0x18002180f  push    rsi
0x180021810  push    rdi
0x180021811  push    r13
0x180021813  sub     rsp, 78h
0x180021817  mov     r13, r8
0x18002181a  mov     ebx, edx
0x18002181c  mov     rdi, rcx
0x18002181f  mov     rcx, cs:WPP_GLOBAL_Control
0x180021826  lea     rsi, WPP_GLOBAL_Control
0x18002182d  cmp     rcx, rsi
0x180021830  jnz     loc_180021A38
0x180021836  mov     [rsp+98h+var_38], r15
0x18002183b  test    rdi, rdi
0x18002183e  jz      loc_180021AB1
0x180021844  test    ebx, ebx
0x180021846  jz      loc_180021AB1
0x18002184c  test    r13, r13
0x18002184f  jz      loc_180021AB1
0x180021855  mov     r15, [rsp+98h+arg_20]
0x18002185d  test    r15, r15
0x180021860  jz      loc_180021AB9
0x180021866  lea     rbx, [r13+10h]
0x18002186a  mov     [rsp+98h+var_30], r14
0x18002186f  mov     rcx, rbx; lpCriticalSection
0x180021872  mov     dword ptr [r15], 0
0x180021879  xor     r14b, r14b
0x18002187c  mov     [rsp+98h+var_48], rbx
0x180021881  call    cs:__imp_EnterCriticalSection
0x180021888  nop     dword ptr [rax+rax+00h]
0x18002188d  mov     eax, [r13+7Ch]
0x180021891  test    eax, eax
0x180021893  js      loc_180021955
0x180021899  and     eax, 60000000h
0x18002189e  cmp     eax, 60000000h
0x1800218a3  jnz     loc_180021955
0x1800218a9  mov     [rsp+98h+var_28], r12
0x1800218ae  xor     r12d, r12d
0x1800218b1  mov     [rsp+98h+var_58], r12d
0x1800218b6  cmp     [r13+80h], r12d
0x1800218bd  jbe     loc_180021950
0x1800218c3  mov     [rsp+98h+arg_10], rbp
0x1800218cb  test    r14b, r14b
0x1800218ce  jnz     short loc_18002193C
0x1800218d0  mov     rsi, [r13+90h]
0x1800218d7  lea     rdi, [r12+r12*4]
0x1800218db  shl     rdi, 4
0x1800218df  add     rsi, rdi
0x1800218e2  mov     [rsp+98h+var_50], rdi
0x1800218e7  cmp     qword ptr [rsi+48h], 0
0x1800218ec  jz      short loc_18002192B
0x1800218ee  mov     eax, [rsi]
0x1800218f0  xor     ebx, ebx
0x1800218f2  mov     [rsp+98h+var_54], eax
0x1800218f6  cmp     [rsi+40h], ebx
0x1800218f9  jbe     short loc_18002192B
0x1800218fb  mov     r12d, dword ptr [rsp+98h+Length]
0x180021903  test    r14b, r14b
0x180021906  jnz     short loc_180021926
0x180021908  mov     eax, ebx
0x18002190a  imul    rbp, rax, 88h
0x180021911  add     rbp, [rsi+48h]
0x180021915  cmp     [rbp+24h], r14b
0x180021919  jnz     loc_180021A6D
0x18002191f  inc     ebx
0x180021921  cmp     ebx, [rsi+40h]
0x180021924  jb      short loc_180021903
0x180021926  mov     r12d, [rsp+98h+var_58]
0x18002192b  inc     r12d
0x18002192e  mov     [rsp+98h+var_58], r12d
0x180021933  cmp     r12d, [r13+80h]
0x18002193a  jb      short loc_1800218CB
0x18002193c  mov     rbx, [rsp+98h+var_48]
0x180021941  lea     rsi, WPP_GLOBAL_Control
0x180021948  mov     rbp, [rsp+98h+arg_10]
0x180021950  mov     r12, [rsp+98h+var_28]
0x180021955  mov     rcx, rbx; lpCriticalSection
0x180021958  call    cs:__imp_LeaveCriticalSection
0x18002195f  nop     dword ptr [rax+rax+00h]
0x180021964  mov     rcx, cs:WPP_GLOBAL_Control
0x18002196b  cmp     rcx, rsi
0x18002196e  jnz     loc_180021A7C
0x180021974  movzx   eax, r14b
0x180021978  mov     r14, [rsp+98h+var_30]
0x18002197d  mov     r15, [rsp+98h+var_38]
0x180021982  add     rsp, 78h
0x180021986  pop     r13
0x180021988  pop     rdi
0x180021989  pop     rsi
0x18002198a  pop     rbx
0x18002198b  retn
0x18002198d  mov     rdi, [rbp+38h]
0x180021991  add     rdi, [rbp+30h]
0x180021995  call    cs:__imp_GetTickCount64
0x18002199c  nop     dword ptr [rax+rax+00h]
0x1800219a1  cmp     rdi, rax
0x1800219a4  jb      loc_18002191F
0x1800219aa  cmp     r12d, [rbp+20h]
0x1800219ae  jnz     loc_18002191F
0x1800219b4  mov     rcx, [rsp+98h+Source1]; Source1
0x1800219bc  mov     r8, r12; Length
0x1800219bf  mov     rdx, rbp; Source2
0x1800219c2  call    cs:__imp_RtlCompareMemory
0x1800219c9  nop     dword ptr [rax+rax+00h]
0x1800219ce  cmp     r12, rax
0x1800219d1  jnz     loc_18002191F
0x1800219d7  mov     eax, [rsp+98h+arg_18]
0x1800219de  cmp     eax, 3
0x1800219e1  jz      short loc_1800219EC
0x1800219e3  cmp     [rbp+28h], eax
0x1800219e6  jnz     loc_18002191F
0x1800219ec  mov     rax, [r13+90h]
0x1800219f3  mov     edx, ebx
0x1800219f5  mov     r8, [rsp+98h+var_50]
0x1800219fa  mov     ecx, [rax+r8+3Ch]
0x1800219ff  mov     eax, [rax+r8+4]
0x180021a04  and     eax, [rsp+98h+var_54]
0x180021a08  shl     edx, cl
0x180021a0a  mov     rcx, [rsp+98h+arg_28]
0x180021a12  or      edx, eax; unsigned int
0x180021a14  mov     [r15], edx
0x180021a17  test    rcx, rcx
0x180021a1a  jz      short loc_180021A21
0x180021a1c  mov     eax, [rbp+28h]
0x180021a1f  mov     [rcx], eax
0x180021a21  mov     r8, rbp; struct _DYNAMIC_ADDRESS *
0x180021a24  lea     rcx, aV2dhcpfindexis; "V2DhcpFindExistingLease found existing"
0x180021a2b  mov     r14b, 1
0x180021a2e  call    ?V2DhcpTraceLease@@YAXPEBDKPEBU_DYNAMIC_ADDRESS@@@Z; V2DhcpTraceLease(char const *,ulong,_DYNAMIC_ADDRESS const *)
0x180021a33  jmp     loc_18002191F
0x180021a38  test    byte ptr [rcx+1Ch], 2
0x180021a3c  jz      loc_180021836
0x180021a42  cmp     byte ptr [rcx+19h], 6
0x180021a46  jb      loc_180021836
0x180021a4c  mov     rcx, [rcx+10h]
0x180021a50  lea     r8, WPP_75f098ceb717321f6a7e914f13ba0684_Traceguids
0x180021a57  mov     edx, 42h ; 'B'
0x180021a5c  call    WPP_SF_L
0x180021a61  mov     rcx, cs:WPP_GLOBAL_Control
0x180021a68  jmp     loc_180021836
0x180021a6d  cmp     byte ptr [rbp+25h], 0
0x180021a71  jz      loc_18002191F
0x180021a77  jmp     loc_18002198D
0x180021a7c  test    byte ptr [rcx+1Ch], 2
0x180021a80  jz      loc_180021974
0x180021a86  cmp     byte ptr [rcx+19h], 6
0x180021a8a  jb      loc_180021974
0x180021a90  mov     rcx, [rcx+10h]
0x180021a94  lea     r8, WPP_75f098ceb717321f6a7e914f13ba0684_Traceguids
0x180021a9b  test    r14b, r14b
0x180021a9e  mov     edx, 45h ; 'E'
0x180021aa3  setnz   r9b
0x180021aa7  call    WPP_SF_c
0x180021aac  jmp     loc_180021974
0x180021ab1  mov     r15, [rsp+98h+arg_20]
0x180021ab9  cmp     rcx, rsi
0x180021abc  jz      short loc_180021AF7
0x180021abe  test    byte ptr [rcx+1Ch], 2
0x180021ac2  jz      short loc_180021AF7
0x180021ac4  cmp     byte ptr [rcx+19h], 4
0x180021ac8  jb      short loc_180021AF7
0x180021aca  mov     rcx, [rcx+10h]
0x180021ace  lea     r8, WPP_75f098ceb717321f6a7e914f13ba0684_Traceguids
0x180021ad5  mov     [rsp+98h+var_68], r15
0x180021ada  mov     edx, 43h ; 'C'
0x180021adf  mov     [rsp+98h+var_70], r13
0x180021ae4  mov     r9, rdi
0x180021ae7  mov     [rsp+98h+var_78], ebx
0x180021aeb  call    WPP_SF_qDqq
0x180021af0  mov     rcx, cs:WPP_GLOBAL_Control
0x180021af7  test    r15, r15
0x180021afa  jz      short loc_180021B0A
0x180021afc  mov     dword ptr [r15], 0
0x180021b03  mov     rcx, cs:WPP_GLOBAL_Control
0x180021b0a  cmp     rcx, rsi
0x180021b0d  jz      short loc_180021B30
0x180021b0f  test    byte ptr [rcx+1Ch], 2
0x180021b13  jz      short loc_180021B30
0x180021b15  cmp     byte ptr [rcx+19h], 6
0x180021b19  jb      short loc_180021B30
0x180021b1b  mov     rcx, [rcx+10h]
0x180021b1f  lea     r8, WPP_75f098ceb717321f6a7e914f13ba0684_Traceguids
0x180021b26  mov     edx, 44h ; 'D'
0x180021b2b  call    WPP_SF_
0x180021b30  xor     al, al
0x180021b32  jmp     loc_18002197D
```
