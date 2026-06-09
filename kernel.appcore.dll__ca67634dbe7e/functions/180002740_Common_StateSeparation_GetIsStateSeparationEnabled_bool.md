# Common::StateSeparation::GetIsStateSeparationEnabled(bool *)

- ea: `0x180002740`
- end: `0x180002840`
- name: `?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z`
- size: `256`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800020d0`

## callees

- `0x180002740`
- `0x18000a010`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18000276a`
- `ntdll!RtlReleaseSRWLockShared` at `0x180002811`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000276a`
- `ntdll!RtlReleaseSRWLockShared` at `0x180002811`
- `ntdll!RtlAcquireSRWLockShared` at `0x180002750`
- `ntdll!RtlAcquireSRWLockShared` at `0x180002750`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180002777`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180002777`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800027ea`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000282f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800027ea`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000282f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000279e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000279e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800027dd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800027dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800027b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800027b6`

## string_xrefs

- `0x180002797`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall Common::StateSeparation::GetIsStateSeparationEnabled(bool *a1)
{
  HMODULE Library; // rax
  HMODULE v3; // rbx
  __int64 (*ProcAddress)(void); // rax
  char v5; // al
  char v6; // al

  RtlAcquireSRWLockShared(&qword_180015748);
  if ( byte_180015751 )
  {
    *a1 = byte_180015750;
    RtlReleaseSRWLockShared(&qword_180015748);
    return 0;
  }
  else
  {
    RtlReleaseSRWLockShared(&qword_180015748);
    RtlAcquireSRWLockExclusive(&qword_180015748);
    if ( byte_180015751 )
    {
      *a1 = byte_180015750;
      RtlReleaseSRWLockExclusive(&qword_180015748);
    }
    else
    {
      Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
      v3 = Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "RtlIsStateSeparationEnabled");
        if ( ProcAddress )
        {
          v5 = ProcAddress();
          byte_180015751 = 1;
          v6 = v5 != 0;
          byte_180015750 = v6;
        }
        else
        {
          v6 = byte_180015750;
        }
        *a1 = v6;
        FreeLibrary(v3);
      }
      else
      {
        *a1 = byte_180015750;
      }
      RtlReleaseSRWLockExclusive(&qword_180015748);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180002740  push    rdi
0x180002742  sub     rsp, 20h
0x180002746  mov     rdi, rcx
0x180002749  lea     rcx, qword_180015748
0x180002750  call    cs:__imp_RtlAcquireSRWLockShared
0x180002756  cmp     cs:byte_180015751, 0
0x18000275d  lea     rcx, qword_180015748
0x180002764  jnz     loc_180002808
0x18000276a  call    cs:__imp_RtlReleaseSRWLockShared
0x180002770  lea     rcx, qword_180015748
0x180002777  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000277d  cmp     cs:byte_180015751, 0
0x180002784  jnz     loc_18000281F
0x18000278a  xor     edx, edx; hFile
0x18000278c  mov     [rsp+28h+arg_0], rbx
0x180002791  mov     r8d, 800h; dwFlags
0x180002797  lea     rcx, ModuleName; "ntdll.dll"
0x18000279e  call    cs:__imp_LoadLibraryExW
0x1800027a4  mov     rbx, rax
0x1800027a7  test    rax, rax
0x1800027aa  jz      short loc_1800027FD
0x1800027ac  lea     rdx, aRtlisstatesepa; "RtlIsStateSeparationEnabled"
0x1800027b3  mov     rcx, rax; hModule
0x1800027b6  call    cs:__imp_GetProcAddress
0x1800027bc  test    rax, rax
0x1800027bf  jz      short loc_180002837
0x1800027c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027c6  test    al, al
0x1800027c8  mov     cs:byte_180015751, 1
0x1800027cf  setnz   al
0x1800027d2  mov     cs:byte_180015750, al
0x1800027d8  mov     rcx, rbx; hLibModule
0x1800027db  mov     [rdi], al
0x1800027dd  call    cs:__imp_FreeLibrary
0x1800027e3  lea     rcx, qword_180015748
0x1800027ea  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800027f0  mov     rbx, [rsp+28h+arg_0]
0x1800027f5  xor     eax, eax
0x1800027f7  add     rsp, 20h
0x1800027fb  pop     rdi
0x1800027fc  retn
0x1800027fd  movzx   eax, cs:byte_180015750
0x180002804  mov     [rdi], al
0x180002806  jmp     short loc_1800027E3
0x180002808  movzx   eax, cs:byte_180015750
0x18000280f  mov     [rdi], al
0x180002811  call    cs:__imp_RtlReleaseSRWLockShared
0x180002817  xor     eax, eax
0x180002819  add     rsp, 20h
0x18000281d  pop     rdi
0x18000281e  retn
0x18000281f  movzx   eax, cs:byte_180015750
0x180002826  lea     rcx, qword_180015748
0x18000282d  mov     [rdi], al
0x18000282f  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002835  jmp     short loc_1800027F5
0x180002837  movzx   eax, cs:byte_180015750
0x18000283e  jmp     short loc_1800027D8
```
