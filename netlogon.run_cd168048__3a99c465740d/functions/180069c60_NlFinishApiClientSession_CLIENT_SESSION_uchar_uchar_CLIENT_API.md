# NlFinishApiClientSession(_CLIENT_SESSION *,uchar,uchar,_CLIENT_API *)

- ea: `0x180069c60`
- end: `0x180069f47`
- name: `?NlFinishApiClientSession@@YAEPEAU_CLIENT_SESSION@@EEPEAU_CLIENT_API@@@Z`
- size: `743`
- prototype: `unsigned __int8 __fastcall(struct _CLIENT_SESSION *, unsigned __int8, unsigned __int8, struct _CLIENT_API *)`
- caller_count: `13`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18002346c`
- `0x18002a8e0`
- `0x180030078`
- `0x180031a3c`
- `0x180033f80`
- `0x180036420`
- `0x1800369f8`
- `0x180036c94`
- `0x180038f68`
- `0x180039ac4`
- `0x18005b2b0`
- `0x18005c514`
- `0x18006e50c`

## callees

- `0x180003ce0`
- `0x180007518`
- `0x18000e910`
- `0x180040f18`
- `0x180069290`
- `0x180069c60`
- `0x18006d2b0`
- `0x180070260`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180069cfb`
- `ntdll!RtlLeaveCriticalSection` at `0x180069d86`
- `ntdll!RtlLeaveCriticalSection` at `0x180069e96`
- `ntdll!RtlLeaveCriticalSection` at `0x180069cfb`
- `ntdll!RtlLeaveCriticalSection` at `0x180069d86`
- `ntdll!RtlLeaveCriticalSection` at `0x180069e96`
- `ntdll!RtlEnterCriticalSection` at `0x180069ca6`
- `ntdll!RtlEnterCriticalSection` at `0x180069d6c`
- `ntdll!RtlEnterCriticalSection` at `0x180069e73`
- `ntdll!RtlEnterCriticalSection` at `0x180069ca6`
- `ntdll!RtlEnterCriticalSection` at `0x180069d6c`
- `ntdll!RtlEnterCriticalSection` at `0x180069e73`
- `ntdll!NtSetInformationThread` at `0x180069f04`
- `ntdll!NtSetInformationThread` at `0x180069f04`

## string_xrefs

- `0x180069f17`: `NlFinishApiClientSession: cannot NtSetInformationThread: 0x%lx\n`

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
    HasElapsed = NetpLogonTimeHasElapsed(v10, (unsigned int)(1000 * (dword_1800F8134 + 15)));
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
                NlDiscoverDc((__int64)a1, 1u, 0, 0);
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
0x180069c60  push    rbx
0x180069c62  push    rbp
0x180069c63  push    rsi
0x180069c64  push    rdi
0x180069c65  push    r12
0x180069c67  push    r13
0x180069c69  push    r14
0x180069c6b  push    r15
0x180069c6d  sub     rsp, 48h
0x180069c71  mov     rax, cs:__security_cookie
0x180069c78  xor     rax, rsp
0x180069c7b  mov     [rsp+88h+var_50], rax
0x180069c80  mov     rdi, rcx
0x180069c83  mov     [rsp+88h+ThreadInformation], 0
0x180069c8c  mov     rcx, [rcx+110h]
0x180069c93  mov     rsi, r9
0x180069c96  add     rcx, 190h; CriticalSection
0x180069c9d  mov     r14b, r8b
0x180069ca0  mov     r13b, dl
0x180069ca3  mov     r15b, 1
0x180069ca6  call    cs:__imp_RtlEnterCriticalSection
0x180069cad  nop     dword ptr [rax+rax+00h]
0x180069cb2  mov     r12d, [rsi+8]
0x180069cb6  or      ecx, 0FFFFFFFFh
0x180069cb9  mov     rbx, [rsi]
0x180069cbc  mov     [rsi+8], ecx
0x180069cbf  test    r14b, r14b
0x180069cc2  jz      short loc_180069CD3
0x180069cc4  mov     eax, [rdi+144h]
0x180069cca  cmp     [rsi+28h], eax
0x180069ccd  jz      loc_180069D78
0x180069cd3  mov     ebp, [rsi+18h]
0x180069cd6  test    r15b, bpl
0x180069cd9  jz      loc_180069D78
0x180069cdf  add     cs:?NlGlobalBindingHandleCount@@3KA, ecx; ulong NlGlobalBindingHandleCount
0x180069ce5  mov     eax, ebp
0x180069ce7  and     eax, 0FFFFFFF8h
0x180069cea  mov     [rsi+18h], eax
0x180069ced  mov     rcx, [rdi+110h]
0x180069cf4  add     rcx, 190h; CriticalSection
0x180069cfb  call    cs:__imp_RtlLeaveCriticalSection
0x180069d02  nop     dword ptr [rax+rax+00h]
0x180069d07  and     bpl, 2
0x180069d0b  mov     rcx, rsi
0x180069d0e  neg     bpl
0x180069d11  mov     rax, 0EA0EA0EA0EA0EA1h
0x180069d1b  sbb     r8d, r8d
0x180069d1e  sub     rcx, rdi
0x180069d21  sub     rcx, 2A8h
0x180069d28  neg     r8d
0x180069d2b  imul    rcx
0x180069d2e  mov     rax, [rsi+20h]
0x180069d32  inc     r8d
0x180069d35  sar     rdx, 5
0x180069d39  mov     rcx, rdi
0x180069d3c  mov     r9, rdx
0x180069d3f  mov     [rsp+88h+var_60], r8d
0x180069d44  shr     r9, 3Fh
0x180069d48  lea     r8, aNlfinishapicli; "NlFinishApiClientSession"
0x180069d4f  add     r9, rdx
0x180069d52  mov     [rsp+88h+var_68], rax
0x180069d57  xor     edx, edx
0x180069d59  call    ?NlpSecureChannelUnbind@@YAXPEAU_CLIENT_SESSION@@PEBGPEBDKPEAXW4_NL_RPC_BINDING@@@Z; NlpSecureChannelUnbind(_CLIENT_SESSION *,ushort const *,char const *,ulong,void *,_NL_RPC_BINDING)
0x180069d5e  mov     rcx, [rdi+110h]
0x180069d65  add     rcx, 190h; CriticalSection
0x180069d6c  call    cs:__imp_RtlEnterCriticalSection
0x180069d73  nop     dword ptr [rax+rax+00h]
0x180069d78  mov     rcx, [rdi+110h]
0x180069d7f  add     rcx, 190h; CriticalSection
0x180069d86  call    cs:__imp_RtlLeaveCriticalSection
0x180069d8d  nop     dword ptr [rax+rax+00h]
0x180069d92  cmp     dword ptr [rdi+118h], 6
0x180069d99  mov     esi, 100h
0x180069d9e  jz      loc_180069EEE
0x180069da4  test    r14b, r14b
0x180069da7  jz      loc_180069EEE
0x180069dad  cmp     r12d, cs:dwMilliseconds
0x180069db4  jnz     loc_180069EEE
0x180069dba  mov     eax, cs:dword_1800F8134
0x180069dc0  mov     rcx, rbx
0x180069dc3  add     eax, 0Fh
0x180069dc6  imul    edx, eax, 3E8h
0x180069dcc  call    NetpLogonTimeHasElapsed
0x180069dd1  mov     ecx, [rdi+1A8h]
0x180069dd7  test    al, al
0x180069dd9  jz      short loc_180069DFE
0x180069ddb  mov     r9, [rdi+1F8h]
0x180069de2  lea     eax, [rcx+1]
0x180069de5  mov     [rdi+1A8h], eax
0x180069deb  lea     r8, aNlfinishapicli_1; "NlFinishApiClientSession: timeout call "...
0x180069df2  mov     dword ptr [rdi+1ACh], 0
0x180069dfc  jmp     short loc_180069E51
0x180069dfe  test    ecx, ecx
0x180069e00  jz      short loc_180069E5F
0x180069e02  mov     edx, 3E8h
0x180069e07  mov     rcx, rbx
0x180069e0a  call    NetpLogonTimeHasElapsed
0x180069e0f  test    al, al
0x180069e11  jz      short loc_180069E5F
0x180069e13  inc     dword ptr [rdi+1ACh]
0x180069e19  mov     eax, [rdi+1ACh]
0x180069e1f  mov     r9, [rdi+1F8h]
0x180069e26  cmp     eax, 5
0x180069e29  jnz     short loc_180069E4A
0x180069e2b  dec     dword ptr [rdi+1A8h]
0x180069e31  lea     r8, aNlfinishapicli_3; "NlFinishApiClientSession: fast call thr"...
0x180069e38  mov     eax, [rdi+1A8h]
0x180069e3e  mov     dword ptr [rdi+1ACh], 0
0x180069e48  jmp     short loc_180069E51
0x180069e4a  lea     r8, aNlfinishapicli_4; "NlFinishApiClientSession: fast call to "...
0x180069e51  mov     rdx, rdi; struct _CLIENT_SESSION *
0x180069e54  mov     dword ptr [rsp+88h+var_68], eax
0x180069e58  mov     ecx, esi; unsigned int
0x180069e5a  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180069e5f  cmp     dword ptr [rdi+1A8h], 2
0x180069e66  jb      loc_180069EEE
0x180069e6c  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180069e73  call    cs:__imp_RtlEnterCriticalSection
0x180069e7a  nop     dword ptr [rax+rax+00h]
0x180069e7f  mov     rcx, [rdi+10h]
0x180069e83  mov     edx, 493E0h
0x180069e88  call    NetpLogonTimeHasElapsed
0x180069e8d  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180069e94  mov     bl, al
0x180069e96  call    cs:__imp_RtlLeaveCriticalSection
0x180069e9d  nop     dword ptr [rax+rax+00h]
0x180069ea2  test    bl, bl
0x180069ea4  jz      short loc_180069EEE
0x180069ea6  mov     r9, [rdi+1F8h]
0x180069ead  lea     r8, aNlfinishapicli_0; "NlFinishApiClientSession: dropping the "...
0x180069eb4  mov     rdx, rdi; struct _CLIENT_SESSION *
0x180069eb7  mov     ecx, esi; unsigned int
0x180069eb9  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180069ebe  xor     r15b, r15b
0x180069ec1  test    r13b, r13b
0x180069ec4  jz      short loc_180069EEE
0x180069ec6  mov     edx, 0C000005Eh; int
0x180069ecb  mov     rcx, rdi; struct _CLIENT_SESSION *
0x180069ece  call    ?NlSetStatusClientSession@@YAXPEAU_CLIENT_SESSION@@J@Z; NlSetStatusClientSession(_CLIENT_SESSION *,long)
0x180069ed3  cmp     cs:?NlGlobalMemberWorkstation@@3HA, 0; int NlGlobalMemberWorkstation
0x180069eda  jnz     short loc_180069EEE
0x180069edc  xor     r9d, r9d
0x180069edf  xor     r8d, r8d
0x180069ee2  mov     rcx, rdi
0x180069ee5  lea     edx, [r9+1]
0x180069ee9  call    ?NlDiscoverDc@@YAJPEAU_CLIENT_SESSION@@W4_DISCOVERY_TYPE@@EE@Z; NlDiscoverDc(_CLIENT_SESSION *,_DISCOVERY_TYPE,uchar,uchar)
0x180069eee  mov     r9d, 8; ThreadInformationLength
0x180069ef4  lea     r8, [rsp+88h+ThreadInformation]; ThreadInformation
0x180069ef9  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180069f00  lea     edx, [r9-3]; ThreadInformationClass
0x180069f04  call    cs:__imp_NtSetInformationThread
0x180069f0b  nop     dword ptr [rax+rax+00h]
0x180069f10  test    eax, eax
0x180069f12  jns     short loc_180069F25
0x180069f14  mov     r8d, eax
0x180069f17  lea     rdx, aNlfinishapicli_2; "NlFinishApiClientSession: cannot NtSetI"...
0x180069f1e  mov     ecx, esi; unsigned int
0x180069f20  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180069f25  mov     al, r15b
0x180069f28  mov     rcx, [rsp+88h+var_50]
0x180069f2d  xor     rcx, rsp; StackCookie
0x180069f30  call    __security_check_cookie
0x180069f35  add     rsp, 48h
0x180069f39  pop     r15
0x180069f3b  pop     r14
0x180069f3d  pop     r13
0x180069f3f  pop     r12
0x180069f41  pop     rdi
0x180069f42  pop     rsi
0x180069f43  pop     rbp
0x180069f44  pop     rbx
0x180069f45  retn
```
