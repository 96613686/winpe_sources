# CPersistDSO::SetSite(IUnknown *)

- ea: `0x180015720`
- end: `0x1800157cb`
- name: `?SetSite@CPersistDSO@@UEAAJPEAUIUnknown@@@Z`
- size: `171`
- prototype: `__int64 __fastcall(CPersistDSO *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180015720`
- `0x18002a830`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001574b`
- `KERNEL32!GetCurrentThreadId` at `0x18001574b`
- `KERNEL32!LeaveCriticalSection` at `0x1800157b3`
- `KERNEL32!LeaveCriticalSection` at `0x1800157b3`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180015769`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180015769`
- `MSDART!UMSEnterCSWraper` at `0x180015739`
- `MSDART!UMSEnterCSWraper` at `0x180015739`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPersistDSO::SetSite(CPersistDSO *this, struct IUnknown *a2)
{
  char *v4; // rbx
  unsigned int v5; // esi
  __int64 v7; // rcx

  v4 = (char *)this - 4488;
  UMSEnterCSWraper((char *)this - 4488);
  if ( !*((_DWORD *)v4 + 3) )
    *((_DWORD *)v4 + 2) = GetCurrentThreadId();
  ++*((_DWORD *)v4 + 3);
  ++*((_DWORD *)v4 + 4);
  SetErrorInfo(0, 0);
  *(GUID *)((char *)this - 4440) = IID_IObjectWithSite;
  *((_DWORD *)this - 81) = 0;
  v5 = CImpIADOSecurity::SetSite(this, a2);
  --*((_DWORD *)v4 + 4);
  if ( (*((_DWORD *)v4 + 3))-- == 1 )
    *((_DWORD *)v4 + 2) = -1;
  v7 = *(_QWORD *)v4;
  --*(_DWORD *)(v7 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 8));
  return v5;
}

```

## disassembly

```asm
0x180015720  push    rbx
0x180015722  push    rbp
0x180015723  push    rsi
0x180015724  push    rdi
0x180015725  sub     rsp, 28h
0x180015729  mov     rbp, rdx
0x18001572c  mov     rsi, rcx
0x18001572f  lea     rbx, [rcx-1188h]
0x180015736  mov     rcx, rbx
0x180015739  call    cs:__imp_UMSEnterCSWraper
0x180015740  nop     dword ptr [rax+rax+00h]
0x180015745  cmp     dword ptr [rbx+0Ch], 0
0x180015749  jnz     short loc_18001575A
0x18001574b  call    cs:__imp_GetCurrentThreadId
0x180015752  nop     dword ptr [rax+rax+00h]
0x180015757  mov     [rbx+8], eax
0x18001575a  inc     dword ptr [rbx+0Ch]
0x18001575d  inc     dword ptr [rbx+10h]
0x180015760  mov     [rsp+48h+arg_0], rbx
0x180015765  xor     edx, edx; perrinfo
0x180015767  xor     ecx, ecx; dwReserved
0x180015769  call    cs:__imp_SetErrorInfo
0x180015770  nop     dword ptr [rax+rax+00h]
0x180015775  movups  xmm0, xmmword ptr cs:IID_IObjectWithSite.Data1
0x18001577c  movdqu  xmmword ptr [rsi-1158h], xmm0
0x180015784  mov     dword ptr [rsi-144h], 0
0x18001578e  mov     rdx, rbp; struct IUnknown *
0x180015791  mov     rcx, rsi; this
0x180015794  call    ?SetSite@CImpIADOSecurity@@UEAAJPEAUIUnknown@@@Z; CImpIADOSecurity::SetSite(IUnknown *)
0x180015799  mov     esi, eax
0x18001579b  or      eax, 0FFFFFFFFh
0x18001579e  add     [rbx+10h], eax
0x1800157a1  add     [rbx+0Ch], eax
0x1800157a4  jnz     short loc_1800157A9
0x1800157a6  mov     [rbx+8], eax
0x1800157a9  mov     rcx, [rbx]
0x1800157ac  dec     dword ptr [rcx+30h]
0x1800157af  add     rcx, 8; lpCriticalSection
0x1800157b3  call    cs:__imp_LeaveCriticalSection
0x1800157ba  nop     dword ptr [rax+rax+00h]
0x1800157bf  mov     eax, esi
0x1800157c1  add     rsp, 28h
0x1800157c5  pop     rdi
0x1800157c6  pop     rsi
0x1800157c7  pop     rbp
0x1800157c8  pop     rbx
0x1800157c9  retn
```
