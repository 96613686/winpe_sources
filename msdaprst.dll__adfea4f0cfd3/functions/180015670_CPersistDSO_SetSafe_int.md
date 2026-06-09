# CPersistDSO::SetSafe(int)

- ea: `0x180015670`
- end: `0x180015714`
- name: `?SetSafe@CPersistDSO@@UEAAJH@Z`
- size: `164`
- prototype: `__int64 __fastcall(CPersistDSO *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180015670`
- `0x18002a7f0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001569a`
- `KERNEL32!GetCurrentThreadId` at `0x18001569a`
- `KERNEL32!LeaveCriticalSection` at `0x1800156fc`
- `KERNEL32!LeaveCriticalSection` at `0x1800156fc`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800156b3`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800156b3`
- `MSDART!UMSEnterCSWraper` at `0x180015688`
- `MSDART!UMSEnterCSWraper` at `0x180015688`

## pseudocode

```c
__int64 __fastcall CPersistDSO::SetSafe(GUID *this, int a2)
{
  GUID *v2; // rbx
  unsigned int v5; // esi
  __int64 v7; // rcx

  v2 = this - 280;
  UMSEnterCSWraper(&this[-280]);
  if ( !*(_DWORD *)&v2->Data4[4] )
    *(_DWORD *)v2->Data4 = GetCurrentThreadId();
  ++*(_DWORD *)&v2->Data4[4];
  ++v2[1].Data1;
  SetErrorInfo(0, 0);
  *(_DWORD *)&this[-20].Data2 = 0;
  this[-277] = IID_IADOSecurity;
  v5 = CImpIADOSecurity::SetSafe((CImpIADOSecurity *)this, a2);
  --v2[1].Data1;
  if ( (*(_DWORD *)&v2->Data4[4])-- == 1 )
    *(_DWORD *)v2->Data4 = -1;
  v7 = *(_QWORD *)&v2->Data1;
  --*(_DWORD *)(v7 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 8));
  return v5;
}

```

## disassembly

```asm
0x180015670  push    rbx
0x180015672  push    rbp
0x180015673  push    rsi
0x180015674  push    rdi
0x180015675  sub     rsp, 28h
0x180015679  lea     rbx, [rcx-1180h]
0x180015680  mov     rsi, rcx
0x180015683  mov     rcx, rbx
0x180015686  mov     ebp, edx
0x180015688  call    cs:__imp_UMSEnterCSWraper
0x18001568f  nop     dword ptr [rax+rax+00h]
0x180015694  cmp     dword ptr [rbx+0Ch], 0
0x180015698  jnz     short loc_1800156A9
0x18001569a  call    cs:__imp_GetCurrentThreadId
0x1800156a1  nop     dword ptr [rax+rax+00h]
0x1800156a6  mov     [rbx+8], eax
0x1800156a9  inc     dword ptr [rbx+0Ch]
0x1800156ac  xor     edx, edx; perrinfo
0x1800156ae  inc     dword ptr [rbx+10h]
0x1800156b1  xor     ecx, ecx; dwReserved
0x1800156b3  call    cs:__imp_SetErrorInfo
0x1800156ba  nop     dword ptr [rax+rax+00h]
0x1800156bf  movups  xmm0, xmmword ptr cs:IID_IADOSecurity.Data1
0x1800156c6  mov     edx, ebp; int
0x1800156c8  mov     dword ptr [rsi-13Ch], 0
0x1800156d2  mov     rcx, rsi; this
0x1800156d5  movdqu  xmmword ptr [rsi-1150h], xmm0
0x1800156dd  call    ?SetSafe@CImpIADOSecurity@@UEAAJH@Z; CImpIADOSecurity::SetSafe(int)
0x1800156e2  mov     esi, eax
0x1800156e4  or      eax, 0FFFFFFFFh
0x1800156e7  add     [rbx+10h], eax
0x1800156ea  add     [rbx+0Ch], eax
0x1800156ed  jnz     short loc_1800156F2
0x1800156ef  mov     [rbx+8], eax
0x1800156f2  mov     rcx, [rbx]
0x1800156f5  dec     dword ptr [rcx+30h]
0x1800156f8  add     rcx, 8; lpCriticalSection
0x1800156fc  call    cs:__imp_LeaveCriticalSection
0x180015703  nop     dword ptr [rax+rax+00h]
0x180015708  mov     eax, esi
0x18001570a  add     rsp, 28h
0x18001570e  pop     rdi
0x18001570f  pop     rsi
0x180015710  pop     rbp
0x180015711  pop     rbx
0x180015712  retn
```
