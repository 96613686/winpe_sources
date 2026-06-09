# BthServRemoveAuthenticationClientByEventHandle(void *,unsigned __int64 *,unsigned __int64)

- ea: `0x1800196d8`
- end: `0x180019aba`
- name: `?BthServRemoveAuthenticationClientByEventHandle@@YAJPEAXPEA_K_K@Z`
- size: `994`
- prototype: `__int64 __fastcall(void *, unsigned __int64 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013220`

## callees

- `0x180011fd0`
- `0x1800120b8`
- `0x180014050`
- `0x180018ca0`
- `0x1800195fc`
- `0x1800196d8`
- `0x18001a678`

## import_xrefs

- `ntdll!RtlRbRemoveNode` at `0x1800198ba`
- `ntdll!RtlRbRemoveNode` at `0x1800198ba`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019777`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019777`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800198d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001994f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019a34`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800198d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001994f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019a34`

## pseudocode

```c
__int64 __fastcall BthServRemoveAuthenticationClientByEventHandle(_QWORD *a1, unsigned __int64 *a2, __int64 a3)
{
  __int64 v3; // r14
  unsigned __int64 v5; // rbx
  char v6; // di
  bool v7; // dl
  int v8; // edx
  int v9; // r8d
  char *v10; // r12
  char *v11; // rsi
  char v12; // cl
  unsigned __int64 v13; // rax
  char *v14; // rbp
  char *v15; // r15
  void *v16; // r13
  int v17; // r14d
  int v18; // eax
  unsigned __int64 v19; // rax
  __int64 v20; // rdx
  char **v21; // rcx
  __int64 v22; // rdx
  char **v23; // rax
  int v24; // r8d
  __int64 *v25; // rdx
  int v27; // r8d
  _QWORD *v28; // rcx
  __int64 *v29; // rdx
  int v30; // [rsp+20h] [rbp-88h]
  int v31; // [rsp+28h] [rbp-80h]
  int v32; // [rsp+30h] [rbp-78h]
  int v33; // [rsp+38h] [rbp-70h]
  __int64 v34; // [rsp+C0h] [rbp+18h]

  v34 = a3;
  v3 = a3;
  v5 = 0;
  v6 = 1;
  v7 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sqi(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      a3,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v30,
      v31,
      20,
      (__int64)WPP_8f95a5b1d9133c17f605a10539329b05_Traceguids);
  }
  if ( WaitForSingleObject(hMutex, 0xFFFFFFFF) )
    return 2147942567LL;
  v10 = (char *)(a1 + 2);
  v11 = (char *)a1[2];
  if ( v11 != (char *)(a1 + 2) )
  {
    v12 = qword_180047090;
    v13 = (unsigned __int64)qword_180047088;
    while ( 1 )
    {
      v14 = v11 - 32;
      v15 = v11;
      if ( *((_QWORD *)v11 + 4) == v3 )
      {
        v16 = (void *)*((_QWORD *)v14 + 1);
        v17 = v12 & 1;
        if ( (v12 & 1) != 0 )
        {
          if ( !v13 )
            goto LABEL_43;
          v5 = v13 ^ (unsigned __int64)&qword_180047088;
        }
        else
        {
          v5 = v13;
        }
        if ( !v5 )
          goto LABEL_43;
        do
        {
          v18 = BthServAuthenticationClientCompare(v16, (struct _RTL_BALANCED_NODE *)v5);
          if ( v18 >= 0 )
          {
            if ( v18 <= 0 )
              break;
            v19 = *(_QWORD *)(v5 + 8);
          }
          else
          {
            v19 = *(_QWORD *)v5;
          }
          if ( v17 && v19 )
            v5 ^= v19;
          else
            v5 = v19;
        }
        while ( v5 );
        v12 = qword_180047090;
        v13 = (unsigned __int64)qword_180047088;
        if ( !v5 )
        {
LABEL_43:
          ReleaseMutex(hMutex);
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
            v6 = 0;
          LOBYTE(v27) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v29 = WPP_8f95a5b1d9133c17f605a10539329b05_Traceguids;
            goto LABEL_63;
          }
          return 2147943568LL;
        }
        v3 = v34;
      }
      v11 = *(char **)v11;
      if ( v11 == v10 )
      {
        if ( !v5 )
          break;
        v20 = *((_QWORD *)v14 + 2);
        if ( *(char **)(v20 + 8) != v14 + 16
          || (v21 = (char **)*((_QWORD *)v14 + 3), *v21 != v14 + 16)
          || (*v21 = (char *)v20,
              *(_QWORD *)(v20 + 8) = v21,
              v22 = *(_QWORD *)v15,
              *(char **)(*(_QWORD *)v15 + 8LL) != v15)
          || (v23 = (char **)*((_QWORD *)v15 + 1), *v23 != v15) )
        {
          __fastfail(3u);
        }
        *v23 = (char *)v22;
        *(_QWORD *)(v22 + 8) = v23;
        BthServReleaseClientResources(v14);
        SdpFreePool(v14);
        if ( *(_QWORD *)(v5 + 40) == v5 + 40 )
        {
          RtlRbRemoveNode(&qword_180047088, v5);
          SdpFreePool(v5);
        }
        ReleaseMutex(hMutex);
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
          v6 = 0;
        if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v25 = WPP_8f95a5b1d9133c17f605a10539329b05_Traceguids;
          LOBYTE(v25) = v6;
          LOBYTE(v24) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)v25,
            v24,
            *((_QWORD *)WPP_GLOBAL_Control + 5));
        }
        return 0;
      }
    }
  }
  LOBYTE(v8) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
  if ( (_BYTE)v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sqqiq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      v9,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v30,
      v31,
      v32,
      v33);
  }
  ReleaseMutex(hMutex);
  v28 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    v6 = 0;
  LOBYTE(v27) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v29 = WPP_8f95a5b1d9133c17f605a10539329b05_Traceguids;
LABEL_63:
    LOBYTE(v29) = v6;
    WPP_RECORDER_AND_TRACE_SF_sD(v28[2], (_DWORD)v29, v27, v28[5]);
  }
  return 2147943568LL;
}

```

## disassembly

```asm
0x1800196d8  mov     rax, rsp
0x1800196db  mov     [rax+20h], rbx
0x1800196df  mov     [rax+18h], r8
0x1800196e3  mov     [rax+10h], rdx
0x1800196e7  mov     [rax+8], rcx
0x1800196eb  push    rbp
0x1800196ec  push    rsi
0x1800196ed  push    rdi
0x1800196ee  push    r12
0x1800196f0  push    r13
0x1800196f2  push    r14
0x1800196f4  push    r15
0x1800196f6  sub     rsp, 70h
0x1800196fa  mov     r14, r8
0x1800196fd  mov     r15, rdx
0x180019700  mov     rbp, rcx
0x180019703  xor     ebx, ebx
0x180019705  mov     rcx, cs:WPP_GLOBAL_Control
0x18001970c  lea     r13, WPP_GLOBAL_Control
0x180019713  lea     edi, [rbx+1]
0x180019716  cmp     rcx, r13
0x180019719  jz      short loc_180019726
0x18001971b  cmp     byte ptr [rcx+19h], 4
0x18001971f  jb      short loc_180019726
0x180019721  mov     dl, dil
0x180019724  jmp     short loc_180019728
0x180019726  xor     dl, dl
0x180019728  lea     rax, WPP_RECORDER_INITIALIZED
0x18001972f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180019736  lea     r9, WPP_8f95a5b1d9133c17f605a10539329b05_Traceguids
0x18001973d  setnz   r8b
0x180019741  test    dl, dl
0x180019743  jnz     short loc_18001974A
0x180019745  test    r8b, r8b
0x180019748  jz      short loc_18001976D
0x18001974a  mov     [rsp+0A8h+var_58], r14
0x18001974f  mov     [rsp+0A8h+var_60], rbp
0x180019754  mov     qword ptr [rsp+0A8h+var_70], r9
0x180019759  mov     r9, [rcx+28h]
0x18001975d  mov     rcx, [rcx+10h]
0x180019761  mov     [rsp+0A8h+var_78], 14h
0x180019768  call    WPP_RECORDER_AND_TRACE_SF_sqi
0x18001976d  mov     rcx, cs:hMutex; hHandle
0x180019774  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180019777  call    cs:__imp_WaitForSingleObject
0x18001977e  nop     dword ptr [rax+rax+00h]
0x180019783  test    eax, eax
0x180019785  jnz     loc_180019A9C
0x18001978b  lea     r12, [rbp+10h]
0x18001978f  mov     rsi, [r12]
0x180019793  cmp     rsi, r12
0x180019796  jz      loc_1800199D5
0x18001979c  mov     rcx, cs:qword_180047090
0x1800197a3  mov     rax, cs:qword_180047088
0x1800197aa  lea     rbp, [rsi-20h]
0x1800197ae  mov     r15, rsi
0x1800197b1  cmp     [rbp+40h], r14
0x1800197b5  jnz     loc_18001983C
0x1800197bb  mov     r13, [rbp+8]
0x1800197bf  movzx   r14d, cl
0x1800197c3  and     r14d, edi
0x1800197c6  test    dil, cl
0x1800197c9  jz      short loc_1800197E0
0x1800197cb  test    rax, rax
0x1800197ce  jz      loc_180019948
0x1800197d4  lea     rbx, qword_180047088
0x1800197db  xor     rbx, rax
0x1800197de  jmp     short loc_1800197E3
0x1800197e0  mov     rbx, rax
0x1800197e3  test    rbx, rbx
0x1800197e6  jz      loc_180019948
0x1800197ec  mov     rdx, rbx; struct _RTL_BALANCED_NODE *
0x1800197ef  mov     rcx, r13; void *
0x1800197f2  call    ?BthServAuthenticationClientCompare@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; BthServAuthenticationClientCompare(void *,_RTL_BALANCED_NODE *)
0x1800197f7  test    eax, eax
0x1800197f9  jns     short loc_180019800
0x1800197fb  mov     rax, [rbx]
0x1800197fe  jmp     short loc_180019806
0x180019800  jle     short loc_18001981D
0x180019802  mov     rax, [rbx+8]
0x180019806  test    r14d, r14d
0x180019809  jz      short loc_180019815
0x18001980b  test    rax, rax
0x18001980e  jz      short loc_180019815
0x180019810  xor     rbx, rax
0x180019813  jmp     short loc_180019818
0x180019815  mov     rbx, rax
0x180019818  test    rbx, rbx
0x18001981b  jnz     short loc_1800197EC
0x18001981d  mov     rcx, cs:qword_180047090
0x180019824  mov     rax, cs:qword_180047088
0x18001982b  test    rbx, rbx
0x18001982e  jz      loc_180019948
0x180019834  mov     r14, [rsp+0A8h+arg_10]
0x18001983c  mov     rsi, [rsi]
0x18001983f  cmp     rsi, r12
0x180019842  jnz     loc_1800197AA
0x180019848  test    rbx, rbx
0x18001984b  jz      loc_1800199BE
0x180019851  lea     rax, [rbp+10h]
0x180019855  mov     rdx, [rax]
0x180019858  cmp     [rdx+8], rax
0x18001985c  jnz     loc_1800199B7
0x180019862  mov     rcx, [rax+8]
0x180019866  cmp     [rcx], rax
0x180019869  jnz     loc_1800199B7
0x18001986f  mov     [rcx], rdx
0x180019872  mov     [rdx+8], rcx
0x180019876  mov     rdx, [r15]
0x180019879  cmp     [rdx+8], r15
0x18001987d  jnz     loc_1800199B7
0x180019883  mov     rax, [r15+8]
0x180019887  cmp     [rax], r15
0x18001988a  jnz     loc_1800199B7
0x180019890  mov     [rax], rdx
0x180019893  mov     rcx, rbp
0x180019896  mov     [rdx+8], rax
0x18001989a  call    BthServReleaseClientResources
0x18001989f  mov     rcx, rbp
0x1800198a2  call    SdpFreePool
0x1800198a7  lea     rax, [rbx+28h]
0x1800198ab  cmp     [rax], rax
0x1800198ae  jnz     short loc_1800198CE
0x1800198b0  mov     rdx, rbx
0x1800198b3  lea     rcx, qword_180047088
0x1800198ba  call    cs:__imp_RtlRbRemoveNode
0x1800198c1  nop     dword ptr [rax+rax+00h]
0x1800198c6  mov     rcx, rbx
0x1800198c9  call    SdpFreePool
0x1800198ce  mov     rcx, cs:hMutex; hMutex
0x1800198d5  call    cs:__imp_ReleaseMutex
0x1800198dc  nop     dword ptr [rax+rax+00h]
0x1800198e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800198e8  lea     rax, WPP_GLOBAL_Control
0x1800198ef  cmp     rcx, rax
0x1800198f2  jz      short loc_1800198FA
0x1800198f4  cmp     byte ptr [rcx+19h], 4
0x1800198f8  jnb     short loc_1800198FD
0x1800198fa  xor     dil, dil
0x1800198fd  lea     rbx, WPP_RECORDER_INITIALIZED
0x180019904  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x18001990b  setnz   r8b
0x18001990f  test    dil, dil
0x180019912  jnz     short loc_180019919
0x180019914  test    r8b, r8b
0x180019917  jz      short loc_180019941
0x180019919  and     dword ptr [rsp+0A8h+var_60], 0
0x18001991e  lea     rdx, WPP_8f95a5b1d9133c17f605a10539329b05_Traceguids
0x180019925  mov     r9, [rcx+28h]
0x180019929  mov     rcx, [rcx+10h]
0x18001992d  mov     qword ptr [rsp+0A8h+var_70], rdx
0x180019932  mov     dl, dil
0x180019935  mov     [rsp+0A8h+var_78], 18h
0x18001993c  call    WPP_RECORDER_AND_TRACE_SF_sD
0x180019941  xor     eax, eax
0x180019943  jmp     loc_180019AA1
0x180019948  mov     rcx, cs:hMutex; hMutex
0x18001994f  call    cs:__imp_ReleaseMutex
0x180019956  nop     dword ptr [rax+rax+00h]
0x18001995b  mov     rcx, cs:WPP_GLOBAL_Control
0x180019962  lea     rax, WPP_GLOBAL_Control
0x180019969  cmp     rcx, rax
0x18001996c  jz      short loc_180019974
0x18001996e  cmp     byte ptr [rcx+19h], 4
0x180019972  jnb     short loc_180019977
0x180019974  xor     dil, dil
0x180019977  lea     rbx, WPP_RECORDER_INITIALIZED
0x18001997e  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x180019985  setnz   r8b
0x180019989  test    dil, dil
0x18001998c  jnz     short loc_180019997
0x18001998e  test    r8b, r8b
0x180019991  jz      loc_180019A95
0x180019997  mov     dword ptr [rsp+0A8h+var_60], 490h
0x18001999f  lea     rdx, WPP_8f95a5b1d9133c17f605a10539329b05_Traceguids
0x1800199a6  mov     qword ptr [rsp+0A8h+var_70], rdx
0x1800199ab  mov     [rsp+0A8h+var_78], 15h
0x1800199b2  jmp     loc_180019A85
0x1800199b7  mov     ecx, 3
0x1800199bc  int     29h; Win8: RtlFailFast(ecx)
0x1800199be  mov     rbp, [rsp+0A8h+arg_0]
0x1800199c6  lea     r13, WPP_GLOBAL_Control
0x1800199cd  mov     r15, [rsp+0A8h+arg_8]
0x1800199d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800199dc  cmp     rcx, r13
0x1800199df  jz      short loc_1800199EC
0x1800199e1  cmp     byte ptr [rcx+19h], 3
0x1800199e5  jb      short loc_1800199EC
0x1800199e7  mov     dl, dil
0x1800199ea  jmp     short loc_1800199EE
0x1800199ec  xor     dl, dl
0x1800199ee  lea     rbx, WPP_RECORDER_INITIALIZED
0x1800199f5  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1800199fc  setnz   r8b
0x180019a00  test    dl, dl
0x180019a02  jnz     short loc_180019A09
0x180019a04  test    r8b, r8b
0x180019a07  jz      short loc_180019A2D
0x180019a09  mov     rax, [r15]
0x180019a0c  mov     r9, [rcx+28h]
0x180019a10  mov     rcx, [rcx+10h]
0x180019a14  mov     [rsp+0A8h+var_48], r14
0x180019a19  mov     [rsp+0A8h+var_50], rax
0x180019a1e  mov     [rsp+0A8h+var_58], r15
0x180019a23  mov     [rsp+0A8h+var_60], rbp
0x180019a28  call    WPP_RECORDER_AND_TRACE_SF_sqqiq
0x180019a2d  mov     rcx, cs:hMutex; hMutex
0x180019a34  call    cs:__imp_ReleaseMutex
0x180019a3b  nop     dword ptr [rax+rax+00h]
0x180019a40  mov     rcx, cs:WPP_GLOBAL_Control
0x180019a47  cmp     rcx, r13
0x180019a4a  jz      short loc_180019A52
0x180019a4c  cmp     byte ptr [rcx+19h], 4
0x180019a50  jnb     short loc_180019A55
0x180019a52  xor     dil, dil
0x180019a55  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x180019a5c  setnz   r8b
0x180019a60  test    dil, dil
0x180019a63  jnz     short loc_180019A6A
0x180019a65  test    r8b, r8b
0x180019a68  jz      short loc_180019A95
0x180019a6a  mov     dword ptr [rsp+0A8h+var_60], 490h
0x180019a72  lea     rdx, WPP_8f95a5b1d9133c17f605a10539329b05_Traceguids
0x180019a79  mov     qword ptr [rsp+0A8h+var_70], rdx
0x180019a7e  mov     [rsp+0A8h+var_78], 17h
0x180019a85  mov     r9, [rcx+28h]
0x180019a89  mov     dl, dil
0x180019a8c  mov     rcx, [rcx+10h]
0x180019a90  call    WPP_RECORDER_AND_TRACE_SF_sD
0x180019a95  mov     eax, 80070490h
0x180019a9a  jmp     short loc_180019AA1
0x180019a9c  mov     eax, 800700A7h
0x180019aa1  mov     rbx, [rsp+0A8h+arg_18]
0x180019aa9  add     rsp, 70h
0x180019aad  pop     r15
0x180019aaf  pop     r14
0x180019ab1  pop     r13
0x180019ab3  pop     r12
0x180019ab5  pop     rdi
0x180019ab6  pop     rsi
0x180019ab7  pop     rbp
0x180019ab8  retn
```
