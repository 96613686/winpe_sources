# V2DhcpFindExistingLease(uchar *,ulong,_V2_DHCP_INTERFACE *,DHCP_LEASE_TYPE,ulong *,DHCP_LEASE_TYPE *)

- ea: `0x180028520`
- end: `0x180028839`
- name: `?V2DhcpFindExistingLease@@YAEPEAEKPEAU_V2_DHCP_INTERFACE@@W4DHCP_LEASE_TYPE@@PEAKPEAW42@@Z`
- size: `793`
- prototype: `char __fastcall(const void *, unsigned int, __int64, int, int *, _DWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004959c`
- `0x180085ff4`

## callees

- `0x180006448`
- `0x18000c110`
- `0x180028520`
- `0x18004215c`
- `0x18005f644`
- `0x18005f684`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800285a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800285a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028675`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028675`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800286ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800286ab`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800286ca`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800286ca`

## pseudocode

```c
char __fastcall V2DhcpFindExistingLease(const void *a1, unsigned int a2, __int64 a3, int a4, int *a5, _DWORD *a6)
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

  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_75f098ceb717321f6a7e914f13ba0684_Traceguids);
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
                        && (a4 == 3 || *(_DWORD *)(v17 + 40) == a4) )
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
0x180028520  mov     [rsp+arg_18], r9d
0x180028525  mov     dword ptr [rsp+Length], edx
0x180028529  mov     [rsp+Source1], rcx
0x18002852e  push    rbx
0x18002852f  push    rsi
0x180028530  push    rdi
0x180028531  push    r13
0x180028533  sub     rsp, 78h
0x180028537  mov     r13, r8
0x18002853a  mov     ebx, edx
0x18002853c  mov     rdi, rcx
0x18002853f  mov     rcx, cs:WPP_GLOBAL_Control
0x180028546  lea     rsi, WPP_GLOBAL_Control
0x18002854d  cmp     rcx, rsi
0x180028550  jnz     loc_18002873A
0x180028556  mov     [rsp+98h+var_38], r15
0x18002855b  test    rdi, rdi
0x18002855e  jz      loc_1800287B3
0x180028564  test    ebx, ebx
0x180028566  jz      loc_1800287B3
0x18002856c  test    r13, r13
0x18002856f  jz      loc_1800287B3
0x180028575  mov     r15, [rsp+98h+arg_20]
0x18002857d  test    r15, r15
0x180028580  jz      loc_1800287BB
0x180028586  lea     rbx, [r13+10h]
0x18002858a  mov     [rsp+98h+var_30], r14
0x18002858f  mov     rcx, rbx; lpCriticalSection
0x180028592  mov     dword ptr [r15], 0
0x180028599  xor     r14b, r14b
0x18002859c  mov     [rsp+98h+var_48], rbx
0x1800285a1  call    cs:__imp_EnterCriticalSection
0x1800285a7  mov     eax, [r13+7Ch]
0x1800285ab  test    eax, eax
0x1800285ad  js      loc_180028672
0x1800285b3  and     eax, 60000000h
0x1800285b8  cmp     eax, 60000000h
0x1800285bd  jnz     loc_180028672
0x1800285c3  mov     [rsp+98h+var_28], r12
0x1800285c8  xor     r12d, r12d
0x1800285cb  mov     [rsp+98h+var_58], r12d
0x1800285d0  cmp     [r13+80h], r12d
0x1800285d7  jbe     loc_18002866D
0x1800285dd  mov     [rsp+98h+arg_10], rbp
0x1800285e5  test    r14b, r14b
0x1800285e8  jnz     short loc_180028659
0x1800285ea  mov     rsi, [r13+90h]
0x1800285f1  lea     rdi, [r12+r12*4]
0x1800285f5  shl     rdi, 4
0x1800285f9  add     rsi, rdi
0x1800285fc  mov     [rsp+98h+var_50], rdi
0x180028601  cmp     qword ptr [rsi+48h], 0
0x180028606  jz      short loc_180028648
0x180028608  mov     eax, [rsi]
0x18002860a  xor     ebx, ebx
0x18002860c  mov     [rsp+98h+var_54], eax
0x180028610  cmp     [rsi+40h], ebx
0x180028613  jbe     short loc_180028648
0x180028615  mov     r12d, dword ptr [rsp+98h+Length]
0x18002861d  nop     dword ptr [rax]
0x180028620  test    r14b, r14b
0x180028623  jnz     short loc_180028643
0x180028625  mov     eax, ebx
0x180028627  imul    rbp, rax, 88h
0x18002862e  add     rbp, [rsi+48h]
0x180028632  cmp     [rbp+24h], r14b
0x180028636  jnz     loc_18002876F
0x18002863c  inc     ebx
0x18002863e  cmp     ebx, [rsi+40h]
0x180028641  jb      short loc_180028620
0x180028643  mov     r12d, [rsp+98h+var_58]
0x180028648  inc     r12d
0x18002864b  mov     [rsp+98h+var_58], r12d
0x180028650  cmp     r12d, [r13+80h]
0x180028657  jb      short loc_1800285E5
0x180028659  mov     rbx, [rsp+98h+var_48]
0x18002865e  lea     rsi, WPP_GLOBAL_Control
0x180028665  mov     rbp, [rsp+98h+arg_10]
0x18002866d  mov     r12, [rsp+98h+var_28]
0x180028672  mov     rcx, rbx; lpCriticalSection
0x180028675  call    cs:__imp_LeaveCriticalSection
0x18002867b  mov     rcx, cs:WPP_GLOBAL_Control
0x180028682  cmp     rcx, rsi
0x180028685  jnz     loc_18002877E
0x18002868b  movzx   eax, r14b
0x18002868f  mov     r14, [rsp+98h+var_30]
0x180028694  mov     r15, [rsp+98h+var_38]
0x180028699  add     rsp, 78h
0x18002869d  pop     r13
0x18002869f  pop     rdi
0x1800286a0  pop     rsi
0x1800286a1  pop     rbx
0x1800286a2  retn
0x1800286a3  mov     rdi, [rbp+38h]
0x1800286a7  add     rdi, [rbp+30h]
0x1800286ab  call    cs:__imp_GetTickCount64
0x1800286b1  cmp     rdi, rax
0x1800286b4  jb      short loc_18002863C
0x1800286b6  cmp     r12d, [rbp+20h]
0x1800286ba  jnz     short loc_18002863C
0x1800286bc  mov     rcx, [rsp+98h+Source1]; Source1
0x1800286c4  mov     r8, r12; Length
0x1800286c7  mov     rdx, rbp; Source2
0x1800286ca  call    cs:__imp_RtlCompareMemory
0x1800286d0  cmp     r12, rax
0x1800286d3  jnz     loc_18002863C
0x1800286d9  mov     eax, [rsp+98h+arg_18]
0x1800286e0  cmp     eax, 3
0x1800286e3  jz      short loc_1800286EE
0x1800286e5  cmp     [rbp+28h], eax
0x1800286e8  jnz     loc_18002863C
0x1800286ee  mov     rax, [r13+90h]
0x1800286f5  mov     edx, ebx
0x1800286f7  mov     r8, [rsp+98h+var_50]
0x1800286fc  mov     ecx, [rax+r8+3Ch]
0x180028701  mov     eax, [rax+r8+4]
0x180028706  and     eax, [rsp+98h+var_54]
0x18002870a  shl     edx, cl
0x18002870c  mov     rcx, [rsp+98h+arg_28]
0x180028714  or      edx, eax; unsigned int
0x180028716  mov     [r15], edx
0x180028719  test    rcx, rcx
0x18002871c  jz      short loc_180028723
0x18002871e  mov     eax, [rbp+28h]
0x180028721  mov     [rcx], eax
0x180028723  mov     r8, rbp; struct _DYNAMIC_ADDRESS *
0x180028726  lea     rcx, aV2dhcpfindexis; "V2DhcpFindExistingLease found existing"
0x18002872d  mov     r14b, 1
0x180028730  call    ?V2DhcpTraceLease@@YAXPEBDKPEBU_DYNAMIC_ADDRESS@@@Z; V2DhcpTraceLease(char const *,ulong,_DYNAMIC_ADDRESS const *)
0x180028735  jmp     loc_18002863C
0x18002873a  test    byte ptr [rcx+1Ch], 2
0x18002873e  jz      loc_180028556
0x180028744  cmp     byte ptr [rcx+19h], 6
0x180028748  jb      loc_180028556
0x18002874e  mov     rcx, [rcx+10h]
0x180028752  lea     r8, WPP_75f098ceb717321f6a7e914f13ba0684_Traceguids
0x180028759  mov     edx, 42h ; 'B'
0x18002875e  call    WPP_SF_L
0x180028763  mov     rcx, cs:WPP_GLOBAL_Control
0x18002876a  jmp     loc_180028556
0x18002876f  cmp     byte ptr [rbp+25h], 0
0x180028773  jz      loc_18002863C
0x180028779  jmp     loc_1800286A3
0x18002877e  test    byte ptr [rcx+1Ch], 2
0x180028782  jz      loc_18002868B
0x180028788  cmp     byte ptr [rcx+19h], 6
0x18002878c  jb      loc_18002868B
0x180028792  mov     rcx, [rcx+10h]
0x180028796  lea     r8, WPP_75f098ceb717321f6a7e914f13ba0684_Traceguids
0x18002879d  test    r14b, r14b
0x1800287a0  mov     edx, 45h ; 'E'
0x1800287a5  setnz   r9b
0x1800287a9  call    WPP_SF_c
0x1800287ae  jmp     loc_18002868B
0x1800287b3  mov     r15, [rsp+98h+arg_20]
0x1800287bb  cmp     rcx, rsi
0x1800287be  jz      short loc_1800287F9
0x1800287c0  test    byte ptr [rcx+1Ch], 2
0x1800287c4  jz      short loc_1800287F9
0x1800287c6  cmp     byte ptr [rcx+19h], 4
0x1800287ca  jb      short loc_1800287F9
0x1800287cc  mov     rcx, [rcx+10h]
0x1800287d0  lea     r8, WPP_75f098ceb717321f6a7e914f13ba0684_Traceguids
0x1800287d7  mov     [rsp+98h+var_68], r15
0x1800287dc  mov     edx, 43h ; 'C'
0x1800287e1  mov     [rsp+98h+var_70], r13
0x1800287e6  mov     r9, rdi
0x1800287e9  mov     [rsp+98h+var_78], ebx
0x1800287ed  call    WPP_SF_qDqq
0x1800287f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800287f9  test    r15, r15
0x1800287fc  jz      short loc_18002880C
0x1800287fe  mov     dword ptr [r15], 0
0x180028805  mov     rcx, cs:WPP_GLOBAL_Control
0x18002880c  cmp     rcx, rsi
0x18002880f  jz      short loc_180028832
0x180028811  test    byte ptr [rcx+1Ch], 2
0x180028815  jz      short loc_180028832
0x180028817  cmp     byte ptr [rcx+19h], 6
0x18002881b  jb      short loc_180028832
0x18002881d  mov     rcx, [rcx+10h]
0x180028821  lea     r8, WPP_75f098ceb717321f6a7e914f13ba0684_Traceguids
0x180028828  mov     edx, 44h ; 'D'
0x18002882d  call    WPP_SF_
0x180028832  xor     al, al
0x180028834  jmp     loc_180028694
```
