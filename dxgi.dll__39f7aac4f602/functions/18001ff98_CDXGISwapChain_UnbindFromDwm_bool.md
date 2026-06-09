# CDXGISwapChain::UnbindFromDwm(bool)

- ea: `0x18001ff98`
- end: `0x18002018c`
- name: `?UnbindFromDwm@CDXGISwapChain@@QEAAX_N@Z`
- size: `500`
- prototype: `void __fastcall(CDXGISwapChain *__hidden this, bool)`
- caller_count: `9`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800202ac`
- `0x180020ad8`
- `0x180021dfc`
- `0x1800286f0`
- `0x18002abd4`
- `0x18004794c`
- `0x18005d590`
- `0x1800c7195`
- `0x1800c71f1`

## callees

- `0x180008680`
- `0x18000c6b0`
- `0x1800137f0`
- `0x18001ff98`
- `0x180020a58`
- `0x180020ab0`
- `0x1800262c4`
- `0x18002e438`
- `0x18002e624`
- `0x180030320`
- `0x18004bf4c`
- `0x18009e814`

## import_xrefs

- `win32u!NtUnBindCompositionSurface` at `0x18001ffdd`
- `win32u!NtUnBindCompositionSurface` at `0x18001ffdd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002004a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020157`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002004a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020157`

## string_xrefs

- `0x180020002`: `UnBindCompositionSurface`
- `0x180020179`: `Cross-adapter fences might be destroyed early, resulting Presents being sent to the DWM before rendering is complete.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CDXGISwapChain::UnbindFromDwm(CDXGISwapChain *this)
{
  __int64 v2; // rcx
  CDXGISwapChain *v3; // rcx
  __int64 v4; // r8
  BOOL v5; // esi
  int v6; // eax
  int v7; // eax
  CModule *v8; // rcx
  int v9; // edi
  __int64 i; // rdi
  void *v11; // rcx
  struct IDXGIFenceInternal *v12; // rdx
  char v13; // r9
  int v14; // eax
  CModule *v15; // rcx

  if ( (unsigned __int8)CDXGISwapChain::IsFlipModel<0>(this) || *(_DWORD *)(v2 + 328) == 3 )
  {
    if ( *(_QWORD *)(v2 + 1224) )
    {
      v5 = (unsigned __int8)CDXGISwapChain::IsFlipModel<1>(v2)
        || !CDXGISwapChain::IsMaximizedWindowedSwapEffectTransitionEnabled(v3)
        || v13;
      v6 = NtUnBindCompositionSurface(v4, v5);
      v7 = HRESULTFromNTSTATUS(v6);
      v9 = v7;
      if ( v7 )
      {
        CModule::RecordJournalImpl(v8, v7, "Contract breached!");
        if ( v9 < 0 )
          CModule::RecordJournalImpl(v8, v9, "UnBindCompositionSurface");
      }
      *((_QWORD *)this + 154) = 0;
      *((_QWORD *)this + 153) = 0;
      if ( v9 >= 0 && (Microsoft_Windows_DXGIEnableBits & 2) != 0 )
        McTemplateU0pq_EtwEventWriteTransfer(v8, EventDXGIUnBindBackBuffersFromDwm, this, v5);
    }
    if ( *((_QWORD *)this + 174) )
    {
      std::unique_ptr<IDXGIFenceInternal,unique_usecntptr_deleter<IDXGIFenceInternal>>::reset((char *)this + 1392, 0);
      CloseHandle(*((HANDLE *)this + 173));
      *((_QWORD *)this + 173) = 0;
      if ( *((_QWORD *)this + 552) )
      {
        ATL::AtlComPtrAssign((struct IUnknown **)this + 552, 0);
        *((_QWORD *)this + 553) = 0;
        *((_QWORD *)this + 554) = 0;
      }
    }
    *((_QWORD *)this + 175) = 0;
    for ( i = 0; i != 17; ++i )
    {
      v11 = (void *)*((_QWORD *)this + i + 156);
      if ( v11 )
        CloseHandle(v11);
      *((_QWORD *)this + i + 156) = 0;
    }
    v12 = (struct IDXGIFenceInternal *)*((_QWORD *)this + 429);
    if ( v12 )
    {
      v14 = CDXGISwapChain::WaitForFenceOnCPU(this, v12, *((_QWORD *)this + 432) - 1LL);
      if ( v14 < 0 )
        CModule::RecordJournalImpl(
          v15,
          v14,
          "Cross-adapter fences might be destroyed early, resulting Presents being sent to the DWM before rendering is complete.");
    }
    CDXGISwapChain::CrossAdapterFence::Release((CDXGISwapChain *)((char *)this + 3432));
    CDXGISwapChain::CrossAdapterFence::Release((CDXGISwapChain *)((char *)this + 3464));
  }
  else if ( *(_QWORD *)(v2 + 232) )
  {
    CDXGISwapChain::IsMaximizedWindowedUpgradesEnabled((CDXGISwapChain *)v2);
  }
}

```

## disassembly

```asm
0x18001ff98  mov     [rsp+arg_0], rbx
0x18001ff9d  mov     [rsp+arg_8], rsi
0x18001ffa2  push    rdi
0x18001ffa3  sub     rsp, 30h
0x18001ffa7  mov     r9b, dl
0x18001ffaa  mov     rbx, rcx
0x18001ffad  call    ??$IsFlipModel@$0A@@CDXGISwapChain@@QEBA_NXZ; CDXGISwapChain::IsFlipModel<0>(void)
0x18001ffb2  test    al, al
0x18001ffb4  jz      loc_1800200D6
0x18001ffba  mov     r8, [rcx+4C8h]
0x18001ffc1  test    r8, r8
0x18001ffc4  jz      short loc_18002002E
0x18001ffc6  call    ??$IsFlipModel@$00@CDXGISwapChain@@QEBA_NXZ; CDXGISwapChain::IsFlipModel<1>(void)
0x18001ffcb  test    al, al
0x18001ffcd  jz      loc_1800200F4
0x18001ffd3  mov     esi, 1
0x18001ffd8  mov     edx, esi
0x18001ffda  mov     rcx, r8
0x18001ffdd  call    cs:__imp_NtUnBindCompositionSurface
0x18001ffe3  mov     ecx, eax; int
0x18001ffe5  call    ?HRESULTFromNTSTATUS@@YAJJ@Z; HRESULTFromNTSTATUS(long)
0x18001ffea  mov     edi, eax
0x18001ffec  test    eax, eax
0x18001ffee  jz      short loc_180020010
0x18001fff0  lea     r8, aContractBreach; "Contract breached!"
0x18001fff7  mov     edx, eax; unsigned int
0x18001fff9  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x18001fffe  test    edi, edi
0x180020000  jns     short loc_180020010
0x180020002  lea     r8, aUnbindcomposit; "UnBindCompositionSurface"
0x180020009  mov     edx, edi; unsigned int
0x18002000b  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x180020010  mov     qword ptr [rbx+4D0h], 0
0x18002001b  mov     qword ptr [rbx+4C8h], 0
0x180020026  test    edi, edi
0x180020028  jns     loc_180020111
0x18002002e  lea     rcx, [rbx+570h]
0x180020035  cmp     qword ptr [rcx], 0
0x180020039  jz      short loc_18002006C
0x18002003b  xor     edx, edx
0x18002003d  call    ?reset@?$unique_ptr@UIDXGIFenceInternal@@U?$unique_usecntptr_deleter@UIDXGIFenceInternal@@@@@std@@QEAAXPEAUIDXGIFenceInternal@@@Z; std::unique_ptr<IDXGIFenceInternal,unique_usecntptr_deleter<IDXGIFenceInternal>>::reset(IDXGIFenceInternal *)
0x180020042  nop
0x180020043  mov     rcx, [rbx+568h]; hObject
0x18002004a  call    cs:__imp_CloseHandle
0x180020050  mov     qword ptr [rbx+568h], 0
0x18002005b  lea     rcx, [rbx+1140h]; struct IUnknown **
0x180020062  cmp     qword ptr [rcx], 0
0x180020066  jnz     loc_180020135
0x18002006c  mov     qword ptr [rbx+578h], 0
0x180020077  xor     edi, edi
0x180020079  mov     rcx, [rbx+rdi*8+4E0h]; hObject
0x180020081  test    rcx, rcx
0x180020084  jnz     loc_180020157
0x18002008a  mov     qword ptr [rbx+rdi*8+4E0h], 0
0x180020096  inc     rdi
0x180020099  cmp     rdi, 11h
0x18002009d  jnz     short loc_180020079
0x18002009f  lea     rdi, [rbx+0D68h]
0x1800200a6  mov     rdx, [rdi]; struct IDXGIFenceInternal *
0x1800200a9  test    rdx, rdx
0x1800200ac  jnz     loc_180020162
0x1800200b2  mov     rcx, rdi; this
0x1800200b5  call    ?Release@CrossAdapterFence@CDXGISwapChain@@QEAAXXZ; CDXGISwapChain::CrossAdapterFence::Release(void)
0x1800200ba  lea     rcx, [rbx+0D88h]; this
0x1800200c1  call    ?Release@CrossAdapterFence@CDXGISwapChain@@QEAAXXZ; CDXGISwapChain::CrossAdapterFence::Release(void)
0x1800200c6  mov     rbx, [rsp+38h+arg_0]
0x1800200cb  mov     rsi, [rsp+38h+arg_8]
0x1800200d0  add     rsp, 30h
0x1800200d4  pop     rdi
0x1800200d5  retn
0x1800200d6  cmp     dword ptr [rcx+148h], 3
0x1800200dd  jz      loc_18001FFBA
0x1800200e3  cmp     qword ptr [rcx+0E8h], 0
0x1800200eb  jz      short loc_1800200C6
0x1800200ed  call    ?IsMaximizedWindowedUpgradesEnabled@CDXGISwapChain@@QEBA_NXZ; CDXGISwapChain::IsMaximizedWindowedUpgradesEnabled(void)
0x1800200f2  jmp     short loc_1800200C6
0x1800200f4  call    ?IsMaximizedWindowedSwapEffectTransitionEnabled@CDXGISwapChain@@QEBA_NXZ; CDXGISwapChain::IsMaximizedWindowedSwapEffectTransitionEnabled(void)
0x1800200f9  test    al, al
0x1800200fb  jz      loc_18001FFD3
0x180020101  test    r9b, r9b
0x180020104  jnz     loc_18001FFD3
0x18002010a  xor     esi, esi
0x18002010c  jmp     loc_18001FFD8
0x180020111  test    byte ptr cs:Microsoft_Windows_DXGIEnableBits, 2
0x180020118  jz      loc_18002002E
0x18002011e  mov     r9d, esi
0x180020121  mov     r8, rbx
0x180020124  lea     rdx, EventDXGIUnBindBackBuffersFromDwm
0x18002012b  call    McTemplateU0pq_EtwEventWriteTransfer
0x180020130  jmp     loc_18002002E
0x180020135  xor     edx, edx; struct IUnknown *
0x180020137  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18002013c  mov     qword ptr [rbx+1148h], 0
0x180020147  mov     qword ptr [rbx+1150h], 0
0x180020152  jmp     loc_18002006C
0x180020157  call    cs:__imp_CloseHandle
0x18002015d  jmp     loc_18002008A
0x180020162  mov     r8, [rdi+18h]
0x180020166  dec     r8; unsigned __int64
0x180020169  mov     rcx, rbx; this
0x18002016c  call    ?WaitForFenceOnCPU@CDXGISwapChain@@QEBAJPEAUIDXGIFenceInternal@@_K@Z; CDXGISwapChain::WaitForFenceOnCPU(IDXGIFenceInternal *,unsigned __int64)
0x180020171  test    eax, eax
0x180020173  jns     loc_1800200B2
0x180020179  lea     r8, aCrossAdapterFe; "Cross-adapter fences might be destroyed"...
0x180020180  mov     edx, eax; unsigned int
0x180020182  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x180020187  jmp     loc_1800200B2
```
