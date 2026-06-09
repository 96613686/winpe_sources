# FWEnumFirewallRules

- ea: `0x18000c3f0`
- end: `0x18000c6e7`
- name: `FWEnumFirewallRules`
- size: `759`
- prototype: ``
- caller_count: `23`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180001edc`
- `0x1800022c0`
- `0x180003080`
- `0x180003e5c`
- `0x180004140`
- `0x1800042c0`
- `0x180004680`
- `0x180007e30`
- `0x180009a50`
- `0x18001e960`
- `0x18001f8c4`
- `0x180021b60`
- `0x180027370`
- `0x180034fe0`
- `0x180035500`
- `0x180035850`
- `0x18003bc1c`
- `0x180045814`
- `0x1800474c8`
- `0x180048d40`
- `0x180049330`
- `0x180049ad8`
- `0x18004b014`

## callees

- `0x180005e0c`
- `0x18000c3f0`
- `0x18000d980`
- `0x1800294b0`
- `0x18003336c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000c450`
- `ntdll!EtwEventWrite` at `0x18000c653`
- `ntdll!EtwEventWrite` at `0x18000c450`
- `ntdll!EtwEventWrite` at `0x18000c653`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000c473`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000c473`

## pseudocode

```c
__int64 __fastcall FWEnumFirewallRules(__int64 a1, int a2, int a3, __int16 a4, __int64 a5, __int64 a6)
{
  unsigned int v10; // ebx
  __int16 v12; // [rsp+30h] [rbp-D0h]
  _QWORD v13[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v14[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int (__fastcall *v15)(void *, void *, unsigned int, unsigned int, unsigned __int16, unsigned int *, void **); // [rsp+70h] [rbp-90h] BYREF
  __int16 v16; // [rsp+78h] [rbp-88h]
  __int64 (__fastcall *v17)(int, int, int, int, __int16, __int64, __int64); // [rsp+80h] [rbp-80h]
  __int16 v18; // [rsp+88h] [rbp-78h]
  __int64 (__fastcall *v19)(int, int, int, int, __int16, __int64, __int64); // [rsp+90h] [rbp-70h]
  __int16 v20; // [rsp+98h] [rbp-68h]
  __int64 (__fastcall *v21)(int, int, int, int, __int16, __int64, __int64); // [rsp+A0h] [rbp-60h]
  __int16 v22; // [rsp+A8h] [rbp-58h]
  __int64 (__fastcall *v23)(int, int, int, int, __int16, __int64, __int64); // [rsp+B0h] [rbp-50h]
  __int16 v24; // [rsp+B8h] [rbp-48h]
  __int64 (__fastcall *v25)(int, int, int, int, __int16, __int64, __int64); // [rsp+C0h] [rbp-40h]
  __int16 v26; // [rsp+C8h] [rbp-38h]
  __int64 (__fastcall *v27)(int, int, int, int, __int16, __int64, __int64); // [rsp+D0h] [rbp-30h]
  __int16 v28; // [rsp+D8h] [rbp-28h]
  __int64 (__fastcall *v29)(int, int, int, int, __int16, __int64, __int64); // [rsp+E0h] [rbp-20h]
  __int16 v30; // [rsp+E8h] [rbp-18h]
  __int64 (__fastcall *v31)(int, int, int, int, __int16, __int64, __int64); // [rsp+F0h] [rbp-10h]
  __int16 v32; // [rsp+F8h] [rbp-8h]
  unsigned int (__fastcall *v33)(void *, void *, unsigned int, unsigned int, unsigned __int16, unsigned int *, void **); // [rsp+100h] [rbp+0h] BYREF
  __int16 v34; // [rsp+108h] [rbp+8h]
  __int64 (__fastcall *v35)(int, int, int, int, __int16, __int64, __int64); // [rsp+110h] [rbp+10h]
  __int16 v36; // [rsp+118h] [rbp+18h]
  __int64 (__fastcall *v37)(int, int, int, int, __int16, __int64, __int64); // [rsp+120h] [rbp+20h]
  __int16 v38; // [rsp+128h] [rbp+28h]
  __int64 (__fastcall *v39)(int, int, int, int, __int16, __int64, __int64); // [rsp+130h] [rbp+30h]
  __int16 v40; // [rsp+138h] [rbp+38h]
  __int64 (__fastcall *v41)(int, int, int, int, __int16, __int64, __int64); // [rsp+140h] [rbp+40h]
  __int16 v42; // [rsp+148h] [rbp+48h]
  __int64 (__fastcall *v43)(int, int, int, int, __int16, __int64, __int64); // [rsp+150h] [rbp+50h]
  __int16 v44; // [rsp+158h] [rbp+58h]
  __int64 (__fastcall *v45)(int, int, int, int, __int16, __int64, __int64); // [rsp+160h] [rbp+60h]
  __int16 v46; // [rsp+168h] [rbp+68h]
  __int64 (__fastcall *v47)(int, int, int, int, __int16, __int64, __int64); // [rsp+170h] [rbp+70h]
  __int16 v48; // [rsp+178h] [rbp+78h]
  __int64 (__fastcall *v49)(int, int, int, int, __int16, __int64, __int64); // [rsp+180h] [rbp+80h]
  __int16 v50; // [rsp+188h] [rbp+88h]

  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_EnumFirewallRules, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  GetTickCount64();
  v15 = Int_RPC_FWEnumFirewallRules2_0;
  v16 = 512;
  v17 = RPC_FWEnumFirewallRules2_10;
  v12 = a4;
  v18 = 522;
  v26 = 538;
  v19 = RPC_FWEnumFirewallRules2_20;
  v28 = 539;
  v21 = RPC_FWEnumFirewallRules2_24;
  v30 = 543;
  v23 = RPC_FWEnumFirewallRules2_25;
  v44 = 538;
  v25 = RPC_FWEnumFirewallRules2_26;
  v46 = 539;
  v27 = RPC_FWEnumFirewallRules2_27;
  v48 = 543;
  v29 = RPC_FWEnumFirewallRules2_31;
  v31 = RPC_FWEnumFirewallRules2_33;
  v14[1] = &v15;
  v33 = Int_RRPC_FWEnumFirewallRules2_0;
  v34 = 512;
  v35 = RRPC_FWEnumFirewallRules2_10;
  v36 = 522;
  v37 = RRPC_FWEnumFirewallRules2_20;
  v39 = RRPC_FWEnumFirewallRules2_24;
  v41 = RRPC_FWEnumFirewallRules2_25;
  v43 = RRPC_FWEnumFirewallRules2_26;
  v45 = RRPC_FWEnumFirewallRules2_27;
  v47 = RRPC_FWEnumFirewallRules2_31;
  v49 = RRPC_FWEnumFirewallRules2_33;
  v13[1] = &v33;
  v20 = 532;
  v22 = 536;
  v24 = 537;
  v32 = 545;
  v14[0] = 9;
  v38 = 532;
  v40 = 536;
  v42 = 537;
  v50 = 545;
  v13[0] = 9;
  v10 = Int_FWEnumObject(0, v14, v13, a1, a2, a3, v12, a5, a6, 0);
  if ( v10 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v10);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_EnumFirewallRules, 0, 0);
  return v10;
}

```

## disassembly

```asm
0x18000c3f0  push    rbp
0x18000c3f2  push    rbx
0x18000c3f3  push    rsi
0x18000c3f4  push    rdi
0x18000c3f5  push    r12
0x18000c3f7  push    r13
0x18000c3f9  push    r14
0x18000c3fb  push    r15
0x18000c3fd  lea     rbp, [rsp-0A8h]
0x18000c405  sub     rsp, 1A8h
0x18000c40c  mov     rax, cs:__security_cookie
0x18000c413  xor     rax, rsp
0x18000c416  mov     [rbp+0E0h+var_50], rax
0x18000c41d  mov     r15, [rbp+0E0h+arg_20]
0x18000c424  mov     rbx, rcx
0x18000c427  mov     rcx, cs:g_Provider
0x18000c42e  movzx   r14d, r9w
0x18000c432  mov     r12, [rbp+0E0h+arg_28]
0x18000c439  mov     esi, r8d
0x18000c43c  mov     edi, edx
0x18000c43e  test    rcx, rcx
0x18000c441  jz      short loc_18000C45C
0x18000c443  xor     r9d, r9d
0x18000c446  lea     rdx, MPS_CLNT_API_Enter_EnumFirewallRules
0x18000c44d  xor     r8d, r8d
0x18000c450  call    cs:__imp_EtwEventWrite
0x18000c457  nop     dword ptr [rax+rax+00h]
0x18000c45c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c463  lea     rax, WPP_GLOBAL_Control
0x18000c46a  cmp     rcx, rax
0x18000c46d  jnz     loc_18000C685
0x18000c473  call    cs:__imp_GetTickCount64
0x18000c47a  nop     dword ptr [rax+rax+00h]
0x18000c47f  lea     rax, ?Int_RPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x18000c486  mov     [rsp+1E0h+var_198], 0
0x18000c48e  mov     [rsp+1E0h+var_170], rax
0x18000c493  mov     r9d, 21Ah
0x18000c499  mov     eax, 200h
0x18000c49e  mov     [rsp+1E0h+var_1A0], r12
0x18000c4a3  mov     [rsp+1E0h+var_168], ax
0x18000c4a8  mov     r8d, 21Bh
0x18000c4ae  lea     rax, RPC_FWEnumFirewallRules2_10
0x18000c4b5  mov     [rsp+1E0h+var_1A8], r15
0x18000c4ba  mov     [rbp+0E0h+var_160], rax
0x18000c4be  mov     edx, 21Fh
0x18000c4c3  mov     eax, 20Ah
0x18000c4c8  mov     [rsp+1E0h+var_1B0], r14w
0x18000c4ce  mov     [rbp+0E0h+var_158], ax
0x18000c4d2  mov     r13d, 214h
0x18000c4d8  lea     rax, RPC_FWEnumFirewallRules2_20
0x18000c4df  mov     [rbp+0E0h+var_118], r9w
0x18000c4e4  mov     [rbp+0E0h+var_150], rax
0x18000c4e8  mov     r11d, 218h
0x18000c4ee  lea     rax, RPC_FWEnumFirewallRules2_24
0x18000c4f5  mov     [rbp+0E0h+var_108], r8w
0x18000c4fa  mov     [rbp+0E0h+var_140], rax
0x18000c4fe  mov     r10d, 219h
0x18000c504  lea     rax, RPC_FWEnumFirewallRules2_25
0x18000c50b  mov     [rbp+0E0h+var_F8], dx
0x18000c50f  mov     [rbp+0E0h+var_130], rax
0x18000c513  mov     ecx, 221h
0x18000c518  lea     rax, RPC_FWEnumFirewallRules2_26
0x18000c51f  mov     [rbp+0E0h+var_88], r9w
0x18000c524  mov     [rbp+0E0h+var_120], rax
0x18000c528  mov     r9, rbx
0x18000c52b  lea     rax, RPC_FWEnumFirewallRules2_27
0x18000c532  mov     [rbp+0E0h+var_78], r8w
0x18000c537  mov     [rbp+0E0h+var_110], rax
0x18000c53b  lea     r8, [rsp+1E0h+var_190]
0x18000c540  lea     rax, RPC_FWEnumFirewallRules2_31
0x18000c547  mov     [rbp+0E0h+var_68], dx
0x18000c54b  mov     [rbp+0E0h+var_100], rax
0x18000c54f  lea     rdx, [rsp+1E0h+var_180]
0x18000c554  lea     rax, RPC_FWEnumFirewallRules2_33
0x18000c55b  mov     [rsp+1E0h+var_1B8], esi
0x18000c55f  mov     [rbp+0E0h+var_F0], rax
0x18000c563  lea     rax, [rsp+1E0h+var_170]
0x18000c568  mov     [rsp+1E0h+var_178], rax
0x18000c56d  lea     rax, ?Int_RRPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RRPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x18000c574  mov     [rbp+0E0h+var_E0], rax
0x18000c578  mov     eax, 200h
0x18000c57d  mov     [rbp+0E0h+var_D8], ax
0x18000c581  lea     rax, RRPC_FWEnumFirewallRules2_10
0x18000c588  mov     [rbp+0E0h+var_D0], rax
0x18000c58c  mov     eax, 20Ah
0x18000c591  mov     [rbp+0E0h+var_C8], ax
0x18000c595  lea     rax, RRPC_FWEnumFirewallRules2_20
0x18000c59c  mov     [rbp+0E0h+var_C0], rax
0x18000c5a0  lea     rax, RRPC_FWEnumFirewallRules2_24
0x18000c5a7  mov     [rbp+0E0h+var_B0], rax
0x18000c5ab  lea     rax, RRPC_FWEnumFirewallRules2_25
0x18000c5b2  mov     [rbp+0E0h+var_A0], rax
0x18000c5b6  lea     rax, RRPC_FWEnumFirewallRules2_26
0x18000c5bd  mov     [rbp+0E0h+var_90], rax
0x18000c5c1  lea     rax, RRPC_FWEnumFirewallRules2_27
0x18000c5c8  mov     [rbp+0E0h+var_80], rax
0x18000c5cc  lea     rax, RRPC_FWEnumFirewallRules2_31
0x18000c5d3  mov     [rbp+0E0h+var_70], rax
0x18000c5d7  lea     rax, RRPC_FWEnumFirewallRules2_33
0x18000c5de  mov     [rbp+0E0h+var_60], rax
0x18000c5e5  lea     rax, [rbp+0E0h+var_E0]
0x18000c5e9  mov     [rsp+1E0h+var_188], rax
0x18000c5ee  mov     [rbp+0E0h+var_148], r13w
0x18000c5f3  mov     [rbp+0E0h+var_138], r11w
0x18000c5f8  mov     [rbp+0E0h+var_128], r10w
0x18000c5fd  mov     [rbp+0E0h+var_E8], cx
0x18000c601  mov     [rsp+1E0h+var_180], 9
0x18000c60a  mov     [rbp+0E0h+var_B8], r13w
0x18000c60f  mov     [rbp+0E0h+var_A8], r11w
0x18000c614  mov     [rbp+0E0h+var_98], r10w
0x18000c619  mov     [rbp+0E0h+var_58], cx
0x18000c620  mov     [rsp+1E0h+var_190], 9
0x18000c629  mov     [rsp+1E0h+var_1C0], edi
0x18000c62d  xor     ecx, ecx
0x18000c62f  call    Int_FWEnumObject
0x18000c634  mov     ebx, eax
0x18000c636  test    eax, eax
0x18000c638  jnz     short loc_18000C6A9
0x18000c63a  mov     rcx, cs:g_Provider
0x18000c641  test    rcx, rcx
0x18000c644  jz      short loc_18000C65F
0x18000c646  xor     r9d, r9d
0x18000c649  lea     rdx, MPS_CLNT_API_Exit_EnumFirewallRules
0x18000c650  xor     r8d, r8d
0x18000c653  call    cs:__imp_EtwEventWrite
0x18000c65a  nop     dword ptr [rax+rax+00h]
0x18000c65f  mov     eax, ebx
0x18000c661  mov     rcx, [rbp+0E0h+var_50]
0x18000c668  xor     rcx, rsp; StackCookie
0x18000c66b  call    __security_check_cookie
0x18000c670  add     rsp, 1A8h
0x18000c677  pop     r15
0x18000c679  pop     r14
0x18000c67b  pop     r13
0x18000c67d  pop     r12
0x18000c67f  pop     rdi
0x18000c680  pop     rsi
0x18000c681  pop     rbx
0x18000c682  pop     rbp
0x18000c683  retn
0x18000c685  test    byte ptr [rcx+1Ch], 8
0x18000c689  jz      loc_18000C473
0x18000c68f  mov     rcx, [rcx+10h]
0x18000c693  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000c69a  mov     edx, 60h ; '`'
0x18000c69f  call    WPP_SF_
0x18000c6a4  jmp     loc_18000C473
0x18000c6a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c6b0  lea     rax, WPP_GLOBAL_Control
0x18000c6b7  cmp     rcx, rax
0x18000c6ba  jz      loc_18000C63A
0x18000c6c0  test    byte ptr [rcx+1Ch], 1
0x18000c6c4  jz      loc_18000C63A
0x18000c6ca  mov     rcx, [rcx+10h]
0x18000c6ce  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000c6d5  mov     edx, 61h ; 'a'
0x18000c6da  mov     r9d, ebx
0x18000c6dd  call    WPP_SF_d
0x18000c6e2  jmp     loc_18000C63A
```
