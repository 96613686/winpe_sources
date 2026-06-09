# FaxOpenService(ushort const *,ushort const *,SC_HANDLE__ * *,SC_HANDLE__ * *,ulong,ulong,ulong *)

- ea: `0x140072604`
- end: `0x14007278f`
- name: `?FaxOpenService@@YAKPEBG0PEAPEAUSC_HANDLE__@@1KKPEAK@Z`
- size: `395`
- prototype: `unsigned int(const unsigned __int16 *, const unsigned __int16 *, struct SC_HANDLE__ **, struct SC_HANDLE__ **, unsigned int, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140072e44`
- `0x140073750`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140072518`
- `0x140072604`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!QueryServiceStatus` at `0x140072710`
- `ADVAPI32!QueryServiceStatus` at `0x140072710`
- `ADVAPI32!OpenSCManagerW` at `0x140072676`
- `ADVAPI32!OpenSCManagerW` at `0x140072676`
- `ADVAPI32!OpenServiceW` at `0x1400726c3`
- `ADVAPI32!OpenServiceW` at `0x1400726c3`
- `KERNEL32!GetLastError` at `0x140072686`
- `KERNEL32!GetLastError` at `0x1400726d1`
- `KERNEL32!GetLastError` at `0x14007271a`
- `KERNEL32!GetLastError` at `0x140072686`
- `KERNEL32!GetLastError` at `0x1400726d1`
- `KERNEL32!GetLastError` at `0x14007271a`

## pseudocode

```c
__int64 __fastcall FaxOpenService(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct SC_HANDLE__ **a3,
        struct SC_HANDLE__ **a4,
        unsigned int a5,
        DWORD dwDesiredAccess,
        unsigned int *a7)
{
  SC_HANDLE v10; // rax
  SC_HANDLE v11; // rsi
  SC_HANDLE v12; // rdi
  DWORD LastError; // eax
  DWORD v14; // ebx
  CMapDeviceId *v15; // rcx
  __int64 v16; // rdx
  SC_HANDLE v17; // rax
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-68h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_db036311db36307996a98c23702218b2_Traceguids);
  }
  v10 = OpenSCManagerW(0, 0, 1u);
  v11 = v10;
  if ( v10 )
  {
    v17 = OpenServiceW(v10, a2, dwDesiredAccess);
    v12 = v17;
    if ( v17 )
    {
      if ( a7 )
      {
        memset(&ServiceStatus, 0, sizeof(ServiceStatus));
        if ( !QueryServiceStatus(v17, &ServiceStatus) )
        {
          LastError = GetLastError();
          v14 = LastError;
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v16 = 13;
            goto LABEL_21;
          }
          goto LABEL_22;
        }
        *a7 = ServiceStatus.dwCurrentState;
      }
      *a3 = v11;
      v14 = 0;
      *a4 = v12;
      return v14;
    }
    LastError = GetLastError();
    v14 = LastError;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = 12;
      goto LABEL_21;
    }
  }
  else
  {
    v12 = 0;
    LastError = GetLastError();
    v14 = LastError;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = 11;
LABEL_21:
      WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_db036311db36307996a98c23702218b2_Traceguids, LastError);
    }
  }
LABEL_22:
  if ( v14 )
    FaxCloseService(v11, v12);
  return v14;
}

```

## disassembly

```asm
0x140072604  push    rbx
0x140072606  push    rbp
0x140072607  push    rsi
0x140072608  push    rdi
0x140072609  push    r13
0x14007260b  push    r14
0x14007260d  push    r15
0x14007260f  sub     rsp, 50h
0x140072613  mov     rax, cs:__security_cookie
0x14007261a  xor     rax, rsp
0x14007261d  mov     [rsp+88h+var_48], rax
0x140072622  mov     ebp, [rsp+88h+dwDesiredAccess]
0x140072629  mov     r15, r9
0x14007262c  mov     rbx, [rsp+88h+arg_30]
0x140072634  mov     r14, r8
0x140072637  mov     rdi, rdx
0x14007263a  mov     rcx, cs:WPP_GLOBAL_Control
0x140072641  lea     r13, WPP_GLOBAL_Control
0x140072648  cmp     rcx, r13
0x14007264b  jz      short loc_14007266E
0x14007264d  test    byte ptr [rcx+1Ch], 2
0x140072651  jz      short loc_14007266E
0x140072653  cmp     byte ptr [rcx+19h], 5
0x140072657  jb      short loc_14007266E
0x140072659  mov     rcx, [rcx+10h]
0x14007265d  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140072664  mov     edx, 0Ah
0x140072669  call    WPP_SF_
0x14007266e  xor     edx, edx; lpDatabaseName
0x140072670  xor     ecx, ecx; lpMachineName
0x140072672  lea     r8d, [rdx+1]; dwDesiredAccess
0x140072676  call    cs:__imp_OpenSCManagerW
0x14007267c  mov     rsi, rax
0x14007267f  test    rax, rax
0x140072682  jnz     short loc_1400726BA
0x140072684  xor     edi, edi
0x140072686  call    cs:__imp_GetLastError
0x14007268c  mov     ebx, eax
0x14007268e  mov     rcx, cs:WPP_GLOBAL_Control
0x140072695  cmp     rcx, r13
0x140072698  jz      loc_140072752
0x14007269e  test    byte ptr [rcx+1Ch], 2
0x1400726a2  jz      loc_140072752
0x1400726a8  cmp     byte ptr [rcx+19h], 2
0x1400726ac  jb      loc_140072752
0x1400726b2  lea     edx, [rsi+0Bh]
0x1400726b5  jmp     loc_14007273F
0x1400726ba  mov     r8d, ebp; dwDesiredAccess
0x1400726bd  mov     rdx, rdi; lpServiceName
0x1400726c0  mov     rcx, rsi; hSCManager
0x1400726c3  call    cs:__imp_OpenServiceW
0x1400726c9  mov     rdi, rax
0x1400726cc  test    rax, rax
0x1400726cf  jnz     short loc_1400726F6
0x1400726d1  call    cs:__imp_GetLastError
0x1400726d7  mov     ebx, eax
0x1400726d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400726e0  cmp     rcx, r13
0x1400726e3  jz      short loc_140072752
0x1400726e5  test    byte ptr [rcx+1Ch], 2
0x1400726e9  jz      short loc_140072752
0x1400726eb  cmp     byte ptr [rcx+19h], 2
0x1400726ef  jb      short loc_140072752
0x1400726f1  lea     edx, [rdi+0Ch]
0x1400726f4  jmp     short loc_14007273F
0x1400726f6  test    rbx, rbx
0x1400726f9  jz      short loc_140072769
0x1400726fb  xorps   xmm0, xmm0
0x1400726fe  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x140072703  movups  xmmword ptr [rsp+88h+ServiceStatus.dwServiceType], xmm0
0x140072708  mov     rcx, rdi; hService
0x14007270b  movups  xmmword ptr [rsp+88h+ServiceStatus.dwWin32ExitCode], xmm0
0x140072710  call    cs:__imp_QueryServiceStatus
0x140072716  test    eax, eax
0x140072718  jnz     short loc_140072763
0x14007271a  call    cs:__imp_GetLastError
0x140072720  mov     ebx, eax
0x140072722  mov     rcx, cs:WPP_GLOBAL_Control
0x140072729  cmp     rcx, r13
0x14007272c  jz      short loc_140072752
0x14007272e  test    byte ptr [rcx+1Ch], 2
0x140072732  jz      short loc_140072752
0x140072734  cmp     byte ptr [rcx+19h], 2
0x140072738  jb      short loc_140072752
0x14007273a  mov     edx, 0Dh
0x14007273f  mov     rcx, [rcx+10h]
0x140072743  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x14007274a  mov     r9d, eax
0x14007274d  call    WPP_SF_d
0x140072752  test    ebx, ebx
0x140072754  jz      short loc_140072771
0x140072756  mov     rdx, rdi; SC_HANDLE
0x140072759  mov     rcx, rsi; hSCObject
0x14007275c  call    ?FaxCloseService@@YAKPEAUSC_HANDLE__@@0@Z; FaxCloseService(SC_HANDLE__ *,SC_HANDLE__ *)
0x140072761  jmp     short loc_140072771
0x140072763  mov     eax, [rsp+88h+ServiceStatus.dwCurrentState]
0x140072767  mov     [rbx], eax
0x140072769  mov     [r14], rsi
0x14007276c  xor     ebx, ebx
0x14007276e  mov     [r15], rdi
0x140072771  mov     eax, ebx
0x140072773  mov     rcx, [rsp+88h+var_48]
0x140072778  xor     rcx, rsp; StackCookie
0x14007277b  call    __security_check_cookie
0x140072780  add     rsp, 50h
0x140072784  pop     r15
0x140072786  pop     r14
0x140072788  pop     r13
0x14007278a  pop     rdi
0x14007278b  pop     rsi
0x14007278c  pop     rbp
0x14007278d  pop     rbx
0x14007278e  retn
```
