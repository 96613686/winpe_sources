# Internal_R_DnsStartMulticastQuery

- ea: `0x180017860`
- end: `0x180017c5a`
- name: `Internal_R_DnsStartMulticastQuery`
- size: `1018`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180017810`

## callees

- `0x18000b130`
- `0x180017860`
- `0x180017e20`
- `0x180017e70`
- `0x180017f4c`
- `0x18001861c`
- `0x180018c68`
- `0x180046ec0`
- `0x18007f9ac`
- `0x180086b1c`
- `0x18008841c`

## import_xrefs

- `ntdll!NtDeleteWnfStateName` at `0x180017b4c`
- `ntdll!NtDeleteWnfStateName` at `0x180017b4c`
- `ntdll!RtlNtStatusToDosError` at `0x180017b8e`
- `ntdll!RtlNtStatusToDosError` at `0x180017b8e`
- `ntdll!NtCreateWnfStateName` at `0x180017915`
- `ntdll!NtCreateWnfStateName` at `0x180017915`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017b7d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017b7d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017b22`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017b22`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017abf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017abf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017a8e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017a8e`

## pseudocode

```c
__int64 __fastcall Internal_R_DnsStartMulticastQuery(__int64 a1, ULONG a2, int a3, __int64 a4, _QWORD *a5)
{
  __int64 v5; // rsi
  ULONG v9; // eax
  ULONG v10; // ebx
  _OWORD *v11; // rbp
  __int64 v12; // rbx
  NTSTATUS v13; // eax
  __int64 v14; // rcx
  _WORD *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdx
  _WORD *v18; // r8
  _WORD *v19; // rcx
  _OWORD *v20; // rax
  __int128 v21; // xmm1
  ULONG v22; // eax
  ULONG v23; // eax
  struct _RTL_CRITICAL_SECTION *v24; // rsi
  QTableNode *Query; // rax
  HANDLE ProcessHeap; // rax
  struct _WNF_STATE_NAME v28; // [rsp+40h] [rbp-58h] BYREF

  v28 = 0;
  v5 = a4;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_qdlq(a1, a2, a3, a1, a2, a3, a4);
  if ( !a1 || !v5 || !*(_QWORD *)(a1 + 8) )
  {
LABEL_42:
    v10 = 87;
    goto LABEL_32;
  }
  v9 = MDns_WaitForInit();
  v10 = v9;
  if ( !v9 )
  {
    if ( g_QueryTable )
    {
      v11 = 0;
      if ( !a5 )
        goto LABEL_9;
      ProcessHeap = g_hProcessHeap;
      if ( !g_hProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        g_hProcessHeap = ProcessHeap;
      }
      v11 = HeapAlloc(ProcessHeap, 8u, 0x20Cu);
      if ( v11 )
      {
LABEL_9:
        v12 = 4;
        v13 = NtCreateWnfStateName(&v28, 3, 0, 0, 0, 4, qword_180094740);
        if ( v13 < 0 )
        {
          v10 = RtlNtStatusToDosError(v13);
        }
        else
        {
          if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
            WPP_SF_Dd(v14, 17, WPP_97f31764ea183d5dd5008a878172189a_Traceguids, v28.Data[0], v28.Data[1]);
          v15 = *(_WORD **)(a1 + 8);
          v16 = 2147483646;
          v17 = 256;
          v18 = (_WORD *)v5;
          do
          {
            if ( !v16 )
              break;
            if ( !*v15 )
              break;
            *v18++ = *v15++;
            --v16;
            --v17;
          }
          while ( v17 );
          v19 = v18 - 1;
          if ( v17 )
            v19 = v18;
          *v19 = 0;
          if ( v17 )
          {
            *(_WORD *)(v5 + 512) = *(_WORD *)(a1 + 16);
            *(struct _WNF_STATE_NAME *)(v5 + 516) = v28;
            v20 = v11;
            do
            {
              *v20 = *(_OWORD *)v5;
              v20[1] = *(_OWORD *)(v5 + 16);
              v20[2] = *(_OWORD *)(v5 + 32);
              v20[3] = *(_OWORD *)(v5 + 48);
              v20[4] = *(_OWORD *)(v5 + 64);
              v20[5] = *(_OWORD *)(v5 + 80);
              v20[6] = *(_OWORD *)(v5 + 96);
              v21 = *(_OWORD *)(v5 + 112);
              v5 += 128;
              v20[7] = v21;
              v20 += 8;
              --v12;
            }
            while ( v12 );
            *(_OWORD *)((char *)v20 - 4) = *(_OWORD *)(v5 - 4);
            v22 = QueryTable::AddQueryAndEntry(
                    (QueryTable *)0x80,
                    *(const unsigned __int16 **)(a1 + 8),
                    *(_WORD *)(a1 + 16),
                    *(_DWORD *)(a1 + 32),
                    *(_QWORD *)(a1 + 24),
                    v28,
                    a2,
                    a3);
            v10 = v22;
            if ( v22 )
            {
              if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
                WPP_SF_d(1035, 19, WPP_97f31764ea183d5dd5008a878172189a_Traceguids, v22);
            }
            else
            {
              v23 = SendMdnsWireQuery(
                      *(_QWORD *)(a1 + 8),
                      *(unsigned __int16 *)(a1 + 16),
                      *(_QWORD *)(a1 + 24),
                      *(_DWORD *)(a1 + 32),
                      a2,
                      a3,
                      0);
              v10 = v23;
              if ( v23 )
              {
                if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
                  WPP_SF_d(1035, 20, WPP_97f31764ea183d5dd5008a878172189a_Traceguids, v23);
                v24 = (struct _RTL_CRITICAL_SECTION *)g_QueryTable;
                EnterCriticalSection((LPCRITICAL_SECTION)g_QueryTable + 1);
                Query = QueryTable::FindQuery(
                          (struct _RTL_CRITICAL_SECTION *)g_QueryTable,
                          *(const unsigned __int16 **)(a1 + 8),
                          *(_WORD *)(a1 + 16));
                if ( Query )
                  QTableNode::RemoveEntry(Query, v28);
                LeaveCriticalSection(v24 + 1);
              }
              else if ( a5 )
              {
                *a5 = v11;
                v11 = 0;
              }
            }
          }
          else
          {
            v10 = 87;
            if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
              WPP_SF_d(1035, 18, WPP_97f31764ea183d5dd5008a878172189a_Traceguids, v17 == 0 ? 0x8007007A : 0);
            NtDeleteWnfStateName(&v28);
          }
        }
        if ( v11 )
          MIDL_user_free(v11);
      }
      else
      {
        v10 = 14;
      }
      goto LABEL_32;
    }
    goto LABEL_42;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
    return v10;
  WPP_SF_d(1035, 16, WPP_97f31764ea183d5dd5008a878172189a_Traceguids, v9);
LABEL_32:
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 21, WPP_97f31764ea183d5dd5008a878172189a_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x180017860  push    rbx
0x180017862  push    rbp
0x180017863  push    rsi
0x180017864  push    rdi
0x180017865  push    r12
0x180017867  push    r13
0x180017869  push    r14
0x18001786b  push    r15
0x18001786d  sub     rsp, 58h
0x180017871  mov     rax, cs:__security_cookie
0x180017878  xor     rax, rsp
0x18001787b  mov     [rsp+98h+var_50], rax
0x180017880  mov     r14, [rsp+98h+arg_20]
0x180017888  xor     r13d, r13d
0x18001788b  mov     qword ptr [rsp+98h+var_58.Data], r13
0x180017890  mov     rsi, r9
0x180017893  mov     r12d, r8d
0x180017896  mov     r15d, edx
0x180017899  mov     rdi, rcx
0x18001789c  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800178a3  jnz     loc_180017B61
0x1800178a9  test    rdi, rdi
0x1800178ac  jz      loc_180017B57
0x1800178b2  test    rsi, rsi
0x1800178b5  jz      loc_180017B57
0x1800178bb  cmp     [rdi+8], r13
0x1800178bf  jz      loc_180017B57
0x1800178c5  call    MDns_WaitForInit
0x1800178ca  mov     ebx, eax
0x1800178cc  test    eax, eax
0x1800178ce  jnz     loc_180017C11
0x1800178d4  cmp     cs:?g_QueryTable@@3PEAVQueryTable@@EA, r13; QueryTable * g_QueryTable
0x1800178db  jz      loc_180017B57
0x1800178e1  mov     rbp, r13
0x1800178e4  test    r14, r14
0x1800178e7  jnz     loc_180017B08
0x1800178ed  mov     ebx, 4
0x1800178f2  lea     rax, qword_180094740
0x1800178f9  mov     qword ptr [rsp+98h+var_68], rax
0x1800178fe  lea     rcx, [rsp+98h+var_58]
0x180017903  mov     [rsp+98h+var_70.Data], ebx
0x180017907  xor     r9d, r9d
0x18001790a  xor     r8d, r8d
0x18001790d  mov     [rsp+98h+var_78], r13
0x180017912  lea     edx, [rbx-1]
0x180017915  call    cs:__imp_NtCreateWnfStateName
0x18001791b  test    eax, eax
0x18001791d  js      loc_180017B8C
0x180017923  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18001792a  jnz     loc_180017B9B
0x180017930  mov     rcx, [rdi+8]
0x180017934  mov     eax, 7FFFFFFEh
0x180017939  mov     edx, 100h
0x18001793e  mov     r8, rsi
0x180017941  test    rax, rax
0x180017944  jz      short loc_180017965
0x180017946  movzx   r9d, word ptr [rcx]
0x18001794a  test    r9w, r9w
0x18001794e  jz      short loc_180017965
0x180017950  mov     [r8], r9w
0x180017954  add     rcx, 2
0x180017958  add     r8, 2
0x18001795c  dec     rax
0x18001795f  sub     rdx, 1
0x180017963  jnz     short loc_180017941
0x180017965  mov     rax, rdx
0x180017968  lea     rcx, [r8-2]
0x18001796c  neg     rax
0x18001796f  sbb     r9d, r9d
0x180017972  not     r9d
0x180017975  and     r9d, 8007007Ah
0x18001797c  test    rdx, rdx
0x18001797f  cmovnz  rcx, r8
0x180017983  mov     [rcx], r13w
0x180017987  jz      loc_180017B39
0x18001798d  movzx   eax, word ptr [rdi+10h]
0x180017991  mov     ecx, 80h; this
0x180017996  mov     [rsi+200h], ax
0x18001799d  mov     rax, qword ptr [rsp+98h+var_58.Data]
0x1800179a2  mov     [rsi+204h], rax
0x1800179a9  mov     rax, rbp
0x1800179ac  movups  xmm0, xmmword ptr [rsi]
0x1800179af  movups  xmmword ptr [rax], xmm0
0x1800179b2  movups  xmm1, xmmword ptr [rsi+10h]
0x1800179b6  movups  xmmword ptr [rax+10h], xmm1
0x1800179ba  movups  xmm0, xmmword ptr [rsi+20h]
0x1800179be  movups  xmmword ptr [rax+20h], xmm0
0x1800179c2  movups  xmm1, xmmword ptr [rsi+30h]
0x1800179c6  movups  xmmword ptr [rax+30h], xmm1
0x1800179ca  movups  xmm0, xmmword ptr [rsi+40h]
0x1800179ce  movups  xmmword ptr [rax+40h], xmm0
0x1800179d2  movups  xmm1, xmmword ptr [rsi+50h]
0x1800179d6  movups  xmmword ptr [rax+50h], xmm1
0x1800179da  movups  xmm0, xmmword ptr [rsi+60h]
0x1800179de  movups  xmmword ptr [rax+60h], xmm0
0x1800179e2  movups  xmm1, xmmword ptr [rsi+70h]
0x1800179e6  add     rsi, rcx
0x1800179e9  movups  xmmword ptr [rax+70h], xmm1
0x1800179ed  add     rax, rcx
0x1800179f0  sub     rbx, 1
0x1800179f4  jnz     short loc_1800179AC
0x1800179f6  movups  xmm0, xmmword ptr [rsi-4]
0x1800179fa  mov     [rsp+98h+var_60], r12d; int
0x1800179ff  mov     [rsp+98h+var_68], r15d; unsigned int
0x180017a04  movups  xmmword ptr [rax-4], xmm0
0x180017a08  mov     rax, qword ptr [rsp+98h+var_58.Data]
0x180017a0d  mov     r9d, [rdi+20h]; unsigned int
0x180017a11  movzx   r8d, word ptr [rdi+10h]; unsigned __int16
0x180017a16  mov     rdx, [rdi+8]; unsigned __int16 *
0x180017a1a  mov     qword ptr [rsp+98h+var_70.Data], rax; struct _WNF_STATE_NAME
0x180017a1f  mov     rax, [rdi+18h]
0x180017a23  mov     [rsp+98h+var_78], rax; unsigned __int64
0x180017a28  call    ?AddQueryAndEntry@QueryTable@@QEAAJPEBGGK_KU_WNF_STATE_NAME@@KH@Z; QueryTable::AddQueryAndEntry(ushort const *,ushort,ulong,unsigned __int64,_WNF_STATE_NAME,ulong,int)
0x180017a2d  mov     ebx, eax
0x180017a2f  test    eax, eax
0x180017a31  jnz     loc_180017BD9
0x180017a37  mov     r9d, [rdi+20h]
0x180017a3b  mov     r8, [rdi+18h]
0x180017a3f  movzx   edx, word ptr [rdi+10h]
0x180017a43  mov     rcx, [rdi+8]
0x180017a47  mov     [rsp+98h+var_68], r13d
0x180017a4c  mov     [rsp+98h+var_70.Data], r12d
0x180017a51  mov     dword ptr [rsp+98h+var_78], r15d
0x180017a56  call    SendMdnsWireQuery
0x180017a5b  mov     ebx, eax
0x180017a5d  test    eax, eax
0x180017a5f  jz      short loc_180017AC7
0x180017a61  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180017a68  jz      short loc_180017A83
0x180017a6a  mov     edx, 14h
0x180017a6f  lea     r8, WPP_97f31764ea183d5dd5008a878172189a_Traceguids
0x180017a76  mov     ecx, 40Bh
0x180017a7b  mov     r9d, eax
0x180017a7e  call    WPP_SF_d
0x180017a83  mov     rsi, cs:?g_QueryTable@@3PEAVQueryTable@@EA; QueryTable * g_QueryTable
0x180017a8a  lea     rcx, [rsi+28h]; lpCriticalSection
0x180017a8e  call    cs:__imp_EnterCriticalSection
0x180017a94  movzx   r8d, word ptr [rdi+10h]; unsigned __int16
0x180017a99  mov     rdx, [rdi+8]; unsigned __int16 *
0x180017a9d  mov     rcx, cs:?g_QueryTable@@3PEAVQueryTable@@EA; this
0x180017aa4  call    ?FindQuery@QueryTable@@QEAAPEAVQTableNode@@PEBGG@Z; QueryTable::FindQuery(ushort const *,ushort)
0x180017aa9  test    rax, rax
0x180017aac  jz      short loc_180017ABB
0x180017aae  mov     rdx, qword ptr [rsp+98h+var_58.Data]; struct _WNF_STATE_NAME
0x180017ab3  mov     rcx, rax; this
0x180017ab6  call    ?RemoveEntry@QTableNode@@QEAAHU_WNF_STATE_NAME@@@Z; QTableNode::RemoveEntry(_WNF_STATE_NAME)
0x180017abb  lea     rcx, [rsi+28h]; lpCriticalSection
0x180017abf  call    cs:__imp_LeaveCriticalSection
0x180017ac5  jmp     short loc_180017AD2
0x180017ac7  test    r14, r14
0x180017aca  jz      short loc_180017AD2
0x180017acc  mov     [r14], rbp
0x180017acf  mov     rbp, r13
0x180017ad2  test    rbp, rbp
0x180017ad5  jnz     loc_180017C04
0x180017adb  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180017ae2  jnz     loc_180017C3C
0x180017ae8  mov     eax, ebx
0x180017aea  mov     rcx, [rsp+98h+var_50]
0x180017aef  xor     rcx, rsp; StackCookie
0x180017af2  call    __security_check_cookie
0x180017af7  add     rsp, 58h
0x180017afb  pop     r15
0x180017afd  pop     r14
0x180017aff  pop     r13
0x180017b01  pop     r12
0x180017b03  pop     rdi
0x180017b04  pop     rsi
0x180017b05  pop     rbp
0x180017b06  pop     rbx
0x180017b07  retn
0x180017b08  mov     rax, cs:g_hProcessHeap
0x180017b0f  test    rax, rax
0x180017b12  jz      short loc_180017B7D
0x180017b14  mov     edx, 8; dwFlags
0x180017b19  mov     r8d, 20Ch; dwBytes
0x180017b1f  mov     rcx, rax; hHeap
0x180017b22  call    cs:__imp_HeapAlloc
0x180017b28  mov     rbp, rax
0x180017b2b  test    rax, rax
0x180017b2e  jnz     loc_1800178ED
0x180017b34  lea     ebx, [rax+0Eh]
0x180017b37  jmp     short loc_180017ADB
0x180017b39  mov     ebx, 57h ; 'W'
0x180017b3e  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180017b45  jnz     short loc_180017BBE
0x180017b47  lea     rcx, [rsp+98h+var_58]
0x180017b4c  call    cs:__imp_NtDeleteWnfStateName
0x180017b52  jmp     loc_180017AD2
0x180017b57  mov     ebx, 57h ; 'W'
0x180017b5c  jmp     loc_180017ADB
0x180017b61  mov     qword ptr [rsp+98h+var_68], rsi
0x180017b66  mov     r9, rdi
0x180017b69  mov     [rsp+98h+var_70.Data], r12d
0x180017b6e  mov     dword ptr [rsp+98h+var_78], r15d
0x180017b73  call    WPP_SF_qdlq
0x180017b78  jmp     loc_1800178A9
0x180017b7d  call    cs:__imp_GetProcessHeap
0x180017b83  mov     cs:g_hProcessHeap, rax
0x180017b8a  jmp     short loc_180017B14
0x180017b8c  mov     ecx, eax; Status
0x180017b8e  call    cs:__imp_RtlNtStatusToDosError
0x180017b94  mov     ebx, eax
0x180017b96  jmp     loc_180017AD2
0x180017b9b  mov     eax, [rsp+98h+var_58.Data+4]
0x180017b9f  lea     r8, WPP_97f31764ea183d5dd5008a878172189a_Traceguids
0x180017ba6  mov     r9d, [rsp+98h+var_58.Data]
0x180017bab  mov     edx, 11h
0x180017bb0  mov     dword ptr [rsp+98h+var_78], eax
0x180017bb4  call    WPP_SF_Dd
0x180017bb9  jmp     loc_180017930
0x180017bbe  mov     edx, 12h
0x180017bc3  lea     r8, WPP_97f31764ea183d5dd5008a878172189a_Traceguids
0x180017bca  mov     ecx, 40Bh
0x180017bcf  call    WPP_SF_d
0x180017bd4  jmp     loc_180017B47
0x180017bd9  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180017be0  jz      loc_180017AD2
0x180017be6  mov     edx, 13h
0x180017beb  lea     r8, WPP_97f31764ea183d5dd5008a878172189a_Traceguids
0x180017bf2  mov     ecx, 40Bh
0x180017bf7  mov     r9d, eax
0x180017bfa  call    WPP_SF_d
0x180017bff  jmp     loc_180017AD2
0x180017c04  mov     rcx, rbp; void *
0x180017c07  call    MIDL_user_free
0x180017c0c  jmp     loc_180017ADB
0x180017c11  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180017c18  jz      loc_180017AE8
0x180017c1e  mov     edx, 10h
0x180017c23  lea     r8, WPP_97f31764ea183d5dd5008a878172189a_Traceguids
0x180017c2a  mov     ecx, 40Bh
0x180017c2f  mov     r9d, eax
0x180017c32  call    WPP_SF_d
0x180017c37  jmp     loc_180017ADB
0x180017c3c  mov     edx, 15h
0x180017c41  lea     r8, WPP_97f31764ea183d5dd5008a878172189a_Traceguids
0x180017c48  mov     ecx, 40Bh
0x180017c4d  mov     r9d, ebx
0x180017c50  call    WPP_SF_d
0x180017c55  jmp     loc_180017AE8
```
