# NlFinishApiClientSession(_CLIENT_SESSION *,uchar,uchar,_CLIENT_API *)

- ea: `0x18006515c`
- end: `0x180065414`
- name: `?NlFinishApiClientSession@@YAEPEAU_CLIENT_SESSION@@EEPEAU_CLIENT_API@@@Z`
- size: `696`
- prototype: `unsigned __int8 __fastcall(struct _CLIENT_SESSION *, unsigned __int8, unsigned __int8, struct _CLIENT_API *)`
- caller_count: `13`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180022374`
- `0x1800291f4`
- `0x18002e478`
- `0x18002fdb4`
- `0x180032160`
- `0x1800344a4`
- `0x180034a68`
- `0x180034cfc`
- `0x180036df8`
- `0x1800378d4`
- `0x180057434`
- `0x1800585a0`
- `0x180069580`

## callees

- `0x180003ac0`
- `0x180007278`
- `0x18000e270`
- `0x18003e71c`
- `0x180064834`
- `0x18006515c`
- `0x180068458`
- `0x18006b1d4`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800651f1`
- `ntdll!RtlLeaveCriticalSection` at `0x180065270`
- `ntdll!RtlLeaveCriticalSection` at `0x180065370`
- `ntdll!RtlLeaveCriticalSection` at `0x1800651f1`
- `ntdll!RtlLeaveCriticalSection` at `0x180065270`
- `ntdll!RtlLeaveCriticalSection` at `0x180065370`
- `ntdll!RtlEnterCriticalSection` at `0x1800651a2`
- `ntdll!RtlEnterCriticalSection` at `0x18006525c`
- `ntdll!RtlEnterCriticalSection` at `0x180065353`
- `ntdll!RtlEnterCriticalSection` at `0x1800651a2`
- `ntdll!RtlEnterCriticalSection` at `0x18006525c`
- `ntdll!RtlEnterCriticalSection` at `0x180065353`
- `ntdll!NtSetInformationThread` at `0x1800653d8`
- `ntdll!NtSetInformationThread` at `0x1800653d8`

## string_xrefs

- `0x1800653e5`: `NlFinishApiClientSession: cannot NtSetInformationThread: 0x%lx\n`

## pseudocode

```c
char __fastcall NlFinishApiClientSession(struct _CLIENT_SESSION *a1, char a2, char a3, struct _CLIENT_API *a4)
{
  char v8; // r15
  int v9; // r12d
  __int64 v10; // rbx
  int v11; // ebp
  char HasElapsed; // al
  int v13; // ecx
  __int64 v14; // r9
  int v15; // eax
  unsigned __int16 *v16; // r8
  char v17; // bl
  __int64 v18; // r8
  char *v19; // r9
  NTSTATUS v20; // eax
  __int64 v22; // [rsp+20h] [rbp-68h]
  __int64 ThreadInformation; // [rsp+30h] [rbp-58h] BYREF

  ThreadInformation = 0;
  v8 = 1;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
  v9 = *((_DWORD *)a4 + 2);
  v10 = *(_QWORD *)a4;
  *((_DWORD *)a4 + 2) = -1;
  if ( !a3 || *((_DWORD *)a4 + 10) != *((_DWORD *)a1 + 81) )
  {
    v11 = *((_DWORD *)a4 + 6);
    if ( (v11 & 1) != 0 )
    {
      --NlGlobalBindingHandleCount;
      *((_DWORD *)a4 + 6) = v11 & 0xFFFFFFF8;
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
      NlpSecureChannelUnbind(
        a1,
        0,
        (__int64)"NlFinishApiClientSession",
        (a4 - a1 - 680) / 560,
        *((RPC_BINDING_HANDLE *)a4 + 4),
        ((v11 & 2) != 0) + 1);
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
    }
  }
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
  if ( *((_DWORD *)a1 + 70) != 6 && a3 && v9 == dwMilliseconds )
  {
    HasElapsed = NetpLogonTimeHasElapsed(v10, (unsigned int)(1000 * (dword_1800F1134 + 15)));
    v13 = *((_DWORD *)a1 + 106);
    if ( HasElapsed )
    {
      v14 = *((_QWORD *)a1 + 63);
      v15 = v13 + 1;
      *((_DWORD *)a1 + 106) = v13 + 1;
      v16 = L"NlFinishApiClientSession: timeout call to %ws.  Count: %lu \n";
      *((_DWORD *)a1 + 107) = 0;
    }
    else
    {
      if ( !v13 || !(unsigned __int8)NetpLogonTimeHasElapsed(v10, 1000) )
      {
LABEL_16:
        if ( *((_DWORD *)a1 + 106) >= 2u )
        {
          RtlEnterCriticalSection(&NlGlobalDcDiscoveryCritSect);
          v17 = NetpLogonTimeHasElapsed(*((_QWORD *)a1 + 2), 300000);
          RtlLeaveCriticalSection(&NlGlobalDcDiscoveryCritSect);
          if ( v17 )
          {
            NlPrintCsRoutine(
              0x100u,
              a1,
              L"NlFinishApiClientSession: dropping the session to %ws\n",
              *((_QWORD *)a1 + 63));
            v8 = 0;
            if ( a2 )
            {
              NlSetStatusClientSession(a1, -1073741730, v18, v19);
              if ( !NlGlobalMemberWorkstation )
                NlDiscoverDc((__int64)a1, 1, 0, 0);
            }
          }
        }
        goto LABEL_21;
      }
      v15 = ++*((_DWORD *)a1 + 107);
      v14 = *((_QWORD *)a1 + 63);
      if ( v15 == 5 )
      {
        --*((_DWORD *)a1 + 106);
        v16 = L"NlFinishApiClientSession: fast call threshold to %ws.  Count: %lu \n";
        v15 = *((_DWORD *)a1 + 106);
        *((_DWORD *)a1 + 107) = 0;
      }
      else
      {
        v16 = L"NlFinishApiClientSession: fast call to %ws.  FastCount: %lu \n";
      }
    }
    LODWORD(v22) = v15;
    NlPrintCsRoutine(0x100u, a1, v16, v14, v22);
    goto LABEL_16;
  }
LABEL_21:
  v20 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  if ( v20 < 0 )
    NlPrintRoutine(0x100u, L"NlFinishApiClientSession: cannot NtSetInformationThread: 0x%lx\n", (unsigned int)v20);
  return v8;
}

```

## disassembly

```asm
0x18006515c  push    rbx
0x18006515e  push    rbp
0x18006515f  push    rsi
0x180065160  push    rdi
0x180065161  push    r12
0x180065163  push    r13
0x180065165  push    r14
0x180065167  push    r15
0x180065169  sub     rsp, 48h
0x18006516d  mov     rax, cs:__security_cookie
0x180065174  xor     rax, rsp
0x180065177  mov     [rsp+88h+var_50], rax
0x18006517c  mov     rdi, rcx
0x18006517f  mov     [rsp+88h+ThreadInformation], 0
0x180065188  mov     rcx, [rcx+110h]
0x18006518f  mov     rsi, r9
0x180065192  add     rcx, 190h; CriticalSection
0x180065199  mov     r14b, r8b
0x18006519c  mov     r13b, dl
0x18006519f  mov     r15b, 1
0x1800651a2  call    cs:__imp_RtlEnterCriticalSection
0x1800651a8  mov     r12d, [rsi+8]
0x1800651ac  or      ecx, 0FFFFFFFFh
0x1800651af  mov     rbx, [rsi]
0x1800651b2  mov     [rsi+8], ecx
0x1800651b5  test    r14b, r14b
0x1800651b8  jz      short loc_1800651C9
0x1800651ba  mov     eax, [rdi+144h]
0x1800651c0  cmp     [rsi+28h], eax
0x1800651c3  jz      loc_180065262
0x1800651c9  mov     ebp, [rsi+18h]
0x1800651cc  test    r15b, bpl
0x1800651cf  jz      loc_180065262
0x1800651d5  add     cs:?NlGlobalBindingHandleCount@@3KA, ecx; ulong NlGlobalBindingHandleCount
0x1800651db  mov     eax, ebp
0x1800651dd  and     eax, 0FFFFFFF8h
0x1800651e0  mov     [rsi+18h], eax
0x1800651e3  mov     rcx, [rdi+110h]
0x1800651ea  add     rcx, 190h; CriticalSection
0x1800651f1  call    cs:__imp_RtlLeaveCriticalSection
0x1800651f7  and     bpl, 2
0x1800651fb  mov     rcx, rsi
0x1800651fe  neg     bpl
0x180065201  mov     rax, 0EA0EA0EA0EA0EA1h
0x18006520b  sbb     r8d, r8d
0x18006520e  sub     rcx, rdi
0x180065211  sub     rcx, 2A8h
0x180065218  neg     r8d
0x18006521b  imul    rcx
0x18006521e  mov     rax, [rsi+20h]
0x180065222  inc     r8d
0x180065225  sar     rdx, 5
0x180065229  mov     rcx, rdi
0x18006522c  mov     r9, rdx
0x18006522f  mov     [rsp+88h+var_60], r8d
0x180065234  shr     r9, 3Fh
0x180065238  lea     r8, aNlfinishapicli; "NlFinishApiClientSession"
0x18006523f  add     r9, rdx
0x180065242  mov     [rsp+88h+var_68], rax
0x180065247  xor     edx, edx
0x180065249  call    ?NlpSecureChannelUnbind@@YAXPEAU_CLIENT_SESSION@@PEBGPEBDKPEAXW4_NL_RPC_BINDING@@@Z; NlpSecureChannelUnbind(_CLIENT_SESSION *,ushort const *,char const *,ulong,void *,_NL_RPC_BINDING)
0x18006524e  mov     rcx, [rdi+110h]
0x180065255  add     rcx, 190h; CriticalSection
0x18006525c  call    cs:__imp_RtlEnterCriticalSection
0x180065262  mov     rcx, [rdi+110h]
0x180065269  add     rcx, 190h; CriticalSection
0x180065270  call    cs:__imp_RtlLeaveCriticalSection
0x180065276  cmp     dword ptr [rdi+118h], 6
0x18006527d  mov     esi, 100h
0x180065282  jz      loc_1800653C2
0x180065288  test    r14b, r14b
0x18006528b  jz      loc_1800653C2
0x180065291  cmp     r12d, cs:dwMilliseconds
0x180065298  jnz     loc_1800653C2
0x18006529e  mov     eax, cs:dword_1800F1134
0x1800652a4  mov     rcx, rbx
0x1800652a7  add     eax, 0Fh
0x1800652aa  imul    edx, eax, 3E8h
0x1800652b0  call    NetpLogonTimeHasElapsed
0x1800652b5  mov     ecx, [rdi+1A8h]
0x1800652bb  test    al, al
0x1800652bd  jz      short loc_1800652E2
0x1800652bf  mov     r9, [rdi+1F8h]
0x1800652c6  lea     eax, [rcx+1]
0x1800652c9  mov     [rdi+1A8h], eax
0x1800652cf  lea     r8, aNlfinishapicli_1; "NlFinishApiClientSession: timeout call "...
0x1800652d6  mov     dword ptr [rdi+1ACh], 0
0x1800652e0  jmp     short loc_180065335
0x1800652e2  test    ecx, ecx
0x1800652e4  jz      short loc_180065343
0x1800652e6  mov     edx, 3E8h
0x1800652eb  mov     rcx, rbx
0x1800652ee  call    NetpLogonTimeHasElapsed
0x1800652f3  test    al, al
0x1800652f5  jz      short loc_180065343
0x1800652f7  inc     dword ptr [rdi+1ACh]
0x1800652fd  mov     eax, [rdi+1ACh]
0x180065303  mov     r9, [rdi+1F8h]
0x18006530a  cmp     eax, 5
0x18006530d  jnz     short loc_18006532E
0x18006530f  dec     dword ptr [rdi+1A8h]
0x180065315  lea     r8, aNlfinishapicli_3; "NlFinishApiClientSession: fast call thr"...
0x18006531c  mov     eax, [rdi+1A8h]
0x180065322  mov     dword ptr [rdi+1ACh], 0
0x18006532c  jmp     short loc_180065335
0x18006532e  lea     r8, aNlfinishapicli_4; "NlFinishApiClientSession: fast call to "...
0x180065335  mov     rdx, rdi; struct _CLIENT_SESSION *
0x180065338  mov     dword ptr [rsp+88h+var_68], eax
0x18006533c  mov     ecx, esi; unsigned int
0x18006533e  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180065343  cmp     dword ptr [rdi+1A8h], 2
0x18006534a  jb      short loc_1800653C2
0x18006534c  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180065353  call    cs:__imp_RtlEnterCriticalSection
0x180065359  mov     rcx, [rdi+10h]
0x18006535d  mov     edx, 493E0h
0x180065362  call    NetpLogonTimeHasElapsed
0x180065367  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18006536e  mov     bl, al
0x180065370  call    cs:__imp_RtlLeaveCriticalSection
0x180065376  test    bl, bl
0x180065378  jz      short loc_1800653C2
0x18006537a  mov     r9, [rdi+1F8h]
0x180065381  lea     r8, aNlfinishapicli_0; "NlFinishApiClientSession: dropping the "...
0x180065388  mov     rdx, rdi; struct _CLIENT_SESSION *
0x18006538b  mov     ecx, esi; unsigned int
0x18006538d  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180065392  xor     r15b, r15b
0x180065395  test    r13b, r13b
0x180065398  jz      short loc_1800653C2
0x18006539a  mov     edx, 0C000005Eh; int
0x18006539f  mov     rcx, rdi; struct _CLIENT_SESSION *
0x1800653a2  call    ?NlSetStatusClientSession@@YAXPEAU_CLIENT_SESSION@@J@Z; NlSetStatusClientSession(_CLIENT_SESSION *,long)
0x1800653a7  cmp     cs:?NlGlobalMemberWorkstation@@3HA, 0; int NlGlobalMemberWorkstation
0x1800653ae  jnz     short loc_1800653C2
0x1800653b0  xor     r9d, r9d
0x1800653b3  xor     r8d, r8d
0x1800653b6  mov     rcx, rdi
0x1800653b9  lea     edx, [r9+1]
0x1800653bd  call    ?NlDiscoverDc@@YAJPEAU_CLIENT_SESSION@@W4_DISCOVERY_TYPE@@EE@Z; NlDiscoverDc(_CLIENT_SESSION *,_DISCOVERY_TYPE,uchar,uchar)
0x1800653c2  mov     r9d, 8; ThreadInformationLength
0x1800653c8  lea     r8, [rsp+88h+ThreadInformation]; ThreadInformation
0x1800653cd  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800653d4  lea     edx, [r9-3]; ThreadInformationClass
0x1800653d8  call    cs:__imp_NtSetInformationThread
0x1800653de  test    eax, eax
0x1800653e0  jns     short loc_1800653F3
0x1800653e2  mov     r8d, eax
0x1800653e5  lea     rdx, aNlfinishapicli_2; "NlFinishApiClientSession: cannot NtSetI"...
0x1800653ec  mov     ecx, esi; unsigned int
0x1800653ee  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800653f3  mov     al, r15b
0x1800653f6  mov     rcx, [rsp+88h+var_50]
0x1800653fb  xor     rcx, rsp; StackCookie
0x1800653fe  call    __security_check_cookie
0x180065403  add     rsp, 48h
0x180065407  pop     r15
0x180065409  pop     r14
0x18006540b  pop     r13
0x18006540d  pop     r12
0x18006540f  pop     rdi
0x180065410  pop     rsi
0x180065411  pop     rbp
0x180065412  pop     rbx
0x180065413  retn
```
