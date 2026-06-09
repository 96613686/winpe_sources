# CChangeListenerRegistrar::~CChangeListenerRegistrar(void)

- ea: `0x18000df94`
- end: `0x18000e03e`
- name: `??1CChangeListenerRegistrar@@QEAA@XZ`
- size: `170`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180034910`

## callees

- `0x180001710`
- `0x180006d60`
- `0x18000df94`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e018`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e018`

## pseudocode

```c
void __fastcall CChangeListenerRegistrar::~CChangeListenerRegistrar(LPCRITICAL_SECTION lpCriticalSection)
{
  LPCRITICAL_SECTION v2; // rdi
  __int64 i; // rdx
  __int64 v4; // rbx
  __int64 v5; // r8
  __int64 v6; // rdx

  v2 = lpCriticalSection + 1;
  if ( *(_QWORD *)&lpCriticalSection[1].LockCount )
  {
    for ( i = 0; (unsigned int)i < LODWORD(lpCriticalSection[1].OwningThread); i = (unsigned int)(i + 1) )
    {
      if ( *((_QWORD *)&v2->DebugInfo->Type + i) )
      {
        _mm_lfence();
        v4 = *((_QWORD *)&v2->DebugInfo->Type + i);
        while ( v4 )
        {
          v5 = v4;
          if ( *(_QWORD *)(v4 + 16) )
          {
            v4 = *(_QWORD *)(v4 + 16);
          }
          else
          {
            LODWORD(v6) = *(_DWORD *)(v4 + 24) % LODWORD(v2->OwningThread);
            do
            {
              v6 = (unsigned int)(v6 + 1);
              v4 = 0;
              if ( (unsigned int)v6 >= LODWORD(v2->OwningThread) )
                break;
              v4 = *((_QWORD *)&v2->DebugInfo->Type + v6);
            }
            while ( !v4 );
          }
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v5 + 8) + 16LL))(*(_QWORD *)(v5 + 8));
        }
        break;
      }
    }
  }
  DeleteCriticalSection(lpCriticalSection);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&lpCriticalSection[2].SpinCount);
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CContentDirectoryChangeListenerForDms *,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<CContentDirectoryChangeListenerForDms *>>::RemoveAll(v2);
}

```

## disassembly

```asm
0x18000df94  mov     [rsp+arg_0], rbx
0x18000df99  mov     [rsp+arg_8], rsi
0x18000df9e  push    rdi
0x18000df9f  sub     rsp, 20h
0x18000dfa3  mov     rsi, rcx
0x18000dfa6  lea     rdi, [rcx+28h]
0x18000dfaa  cmp     qword ptr [rdi+8], 0
0x18000dfaf  jz      short loc_18000E015
0x18000dfb1  xor     edx, edx
0x18000dfb3  cmp     edx, [rdi+10h]
0x18000dfb6  jnb     short loc_18000E015
0x18000dfb8  mov     rax, [rdi]
0x18000dfbb  cmp     qword ptr [rax+rdx*8], 0
0x18000dfc0  jnz     short loc_18000DFC6
0x18000dfc2  inc     edx
0x18000dfc4  jmp     short loc_18000DFB3
0x18000dfc6  lfence
0x18000dfc9  mov     rax, [rdi]
0x18000dfcc  mov     rbx, [rax+rdx*8]
0x18000dfd0  jmp     short loc_18000E010
0x18000dfd2  lea     r8, [rbx]
0x18000dfd5  mov     rax, [rbx+10h]
0x18000dfd9  test    rax, rax
0x18000dfdc  jz      short loc_18000DFE3
0x18000dfde  mov     rbx, rax
0x18000dfe1  jmp     short loc_18000E000
0x18000dfe3  xor     edx, edx
0x18000dfe5  mov     eax, [rbx+18h]
0x18000dfe8  div     dword ptr [rdi+10h]
0x18000dfeb  inc     edx
0x18000dfed  xor     ebx, ebx
0x18000dfef  cmp     edx, [rdi+10h]
0x18000dff2  jnb     short loc_18000E000
0x18000dff4  mov     rax, [rdi]
0x18000dff7  mov     rbx, [rax+rdx*8]
0x18000dffb  test    rbx, rbx
0x18000dffe  jz      short loc_18000DFEB
0x18000e000  mov     rcx, [r8+8]
0x18000e004  mov     rax, [rcx]
0x18000e007  mov     rax, [rax+10h]
0x18000e00b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e010  test    rbx, rbx
0x18000e013  jnz     short loc_18000DFD2
0x18000e015  mov     rcx, rsi; lpCriticalSection
0x18000e018  call    cs:__imp_DeleteCriticalSection
0x18000e01e  lea     rcx, [rsi+70h]
0x18000e022  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000e027  mov     rcx, rdi
0x18000e02a  mov     rbx, [rsp+28h+arg_0]
0x18000e02f  mov     rsi, [rsp+28h+arg_8]
0x18000e034  add     rsp, 20h
0x18000e038  pop     rdi
0x18000e039  jmp     ?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCContentDirectoryChangeListenerForDms@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAVCContentDirectoryChangeListenerForDms@@@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CContentDirectoryChangeListenerForDms *,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CContentDirectoryChangeListenerForDms *>>::RemoveAll(void)
```
