# CPersistDSO::SetURL(ushort *)

- ea: `0x1800157e0`
- end: `0x180015886`
- name: `?SetURL@CPersistDSO@@UEAAJPEAG@Z`
- size: `166`
- prototype: `__int64 __fastcall(CPersistDSO *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800157e0`
- `0x18002a8a0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001580b`
- `KERNEL32!GetCurrentThreadId` at `0x18001580b`
- `KERNEL32!LeaveCriticalSection` at `0x18001586e`
- `KERNEL32!LeaveCriticalSection` at `0x18001586e`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180015824`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180015824`
- `MSDART!UMSEnterCSWraper` at `0x1800157f9`
- `MSDART!UMSEnterCSWraper` at `0x1800157f9`

## pseudocode

```c
__int64 __fastcall CPersistDSO::SetURL(GUID *this, unsigned __int16 *a2)
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
  v5 = CImpIADOSecurity::SetURL((CImpIADOSecurity *)this, a2);
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
0x1800157e0  push    rbx
0x1800157e2  push    rbp
0x1800157e3  push    rsi
0x1800157e4  push    rdi
0x1800157e5  sub     rsp, 28h
0x1800157e9  lea     rbx, [rcx-1180h]
0x1800157f0  mov     rsi, rcx
0x1800157f3  mov     rcx, rbx
0x1800157f6  mov     rbp, rdx
0x1800157f9  call    cs:__imp_UMSEnterCSWraper
0x180015800  nop     dword ptr [rax+rax+00h]
0x180015805  cmp     dword ptr [rbx+0Ch], 0
0x180015809  jnz     short loc_18001581A
0x18001580b  call    cs:__imp_GetCurrentThreadId
0x180015812  nop     dword ptr [rax+rax+00h]
0x180015817  mov     [rbx+8], eax
0x18001581a  inc     dword ptr [rbx+0Ch]
0x18001581d  xor     edx, edx; perrinfo
0x18001581f  inc     dword ptr [rbx+10h]
0x180015822  xor     ecx, ecx; dwReserved
0x180015824  call    cs:__imp_SetErrorInfo
0x18001582b  nop     dword ptr [rax+rax+00h]
0x180015830  movups  xmm0, xmmword ptr cs:IID_IADOSecurity.Data1
0x180015837  mov     rdx, rbp; unsigned __int16 *
0x18001583a  mov     dword ptr [rsi-13Ch], 0
0x180015844  mov     rcx, rsi; this
0x180015847  movdqu  xmmword ptr [rsi-1150h], xmm0
0x18001584f  call    ?SetURL@CImpIADOSecurity@@UEAAJPEAG@Z; CImpIADOSecurity::SetURL(ushort *)
0x180015854  mov     esi, eax
0x180015856  or      eax, 0FFFFFFFFh
0x180015859  add     [rbx+10h], eax
0x18001585c  add     [rbx+0Ch], eax
0x18001585f  jnz     short loc_180015864
0x180015861  mov     [rbx+8], eax
0x180015864  mov     rcx, [rbx]
0x180015867  dec     dword ptr [rcx+30h]
0x18001586a  add     rcx, 8; lpCriticalSection
0x18001586e  call    cs:__imp_LeaveCriticalSection
0x180015875  nop     dword ptr [rax+rax+00h]
0x18001587a  mov     eax, esi
0x18001587c  add     rsp, 28h
0x180015880  pop     rdi
0x180015881  pop     rsi
0x180015882  pop     rbp
0x180015883  pop     rbx
0x180015884  retn
```
