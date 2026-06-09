# CPortClient::SendComplexAsyncRequest(ulong,void const *,short)

- ea: `0x180007ae0`
- end: `0x180007c45`
- name: `?SendComplexAsyncRequest@CPortClient@@QEAAJKPEBXF@Z`
- size: `357`
- prototype: `__int64 __fastcall(CPortClient *__hidden this, unsigned int, const void *, __int16)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ade0`

## callees

- `0x18000352c`
- `0x180007ae0`
- `0x18000b25c`
- `0x18000ddac`
- `0x180015514`

## import_xrefs

- `ntdll!NtAlpcSendWaitReceivePort` at `0x180007b90`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180007b90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007bb0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007bb0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007b1c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007b1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007bbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007bbe`

## pseudocode

```c
__int64 __fastcall CPortClient::SendComplexAsyncRequest(CPortClient *this, int a2, const void *a3, __int16 a4)
{
  size_t v4; // rsi
  unsigned int v8; // ebx
  HANDLE ProcessHeap; // rax
  char *v10; // rax
  void *v11; // rdx
  __int64 v12; // r8
  char *v13; // rdi
  unsigned int v14; // ebx
  int v15; // r9d
  HANDLE v16; // rax
  void *v18; // [rsp+28h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v4 = a4;
  if ( a3 )
  {
    v8 = (unsigned __int16)(a4 + 48);
    ProcessHeap = GetProcessHeap();
    v10 = (char *)HeapAlloc(ProcessHeap, 8u, v8);
    v13 = v10;
    if ( v10 )
    {
      *((_DWORD *)v10 + 10) = a2;
      *(_WORD *)v10 = v4 + 8;
      *((_WORD *)v10 + 1) = v4 + 48;
      if ( (__int16)(v4 + 48) > 512 )
        wil::details::in1diag3::Log_Hr(retaddr, v11, v12, (const char *)0x8007029CLL);
      memcpy_0(v13 + 48, a3, v4);
      v14 = NtAlpcSendWaitReceivePort(*((_QWORD *)this + 2), 0x10000, v13, 0, 0) | 0x10000000;
      CPortClient::CheckHRESULT(this, v14);
      if ( v15 < 0 )
        MilInstrumentationCheckHR_MaybeFailFast(4u, &CPortClient::MILINSTRUMENTATIONHRESULTLIST, 9u, v14, 0x19Cu, 0);
      else
        v14 = 0;
      v16 = GetProcessHeap();
      HeapFree(v16, 0, v13);
    }
    else
    {
      v14 = -2147024882;
      MilInstrumentationCheckHR_MaybeFailFast(
        4u,
        &CPortClient::MILINSTRUMENTATIONHRESULTLIST,
        9u,
        -2147024882,
        0x18Bu,
        v18);
    }
  }
  else
  {
    v14 = -2147024890;
    MilInstrumentationCheckHR_MaybeFailFast(
      4u,
      &CPortClient::MILINSTRUMENTATIONHRESULTLIST,
      9u,
      -2147024890,
      0x188u,
      v18);
  }
  return v14;
}

```

## disassembly

```asm
0x180007ae0  push    rbx
0x180007ae2  push    rbp
0x180007ae3  push    rsi
0x180007ae4  push    rdi
0x180007ae5  push    r14
0x180007ae7  push    r15
0x180007ae9  sub     rsp, 48h
0x180007aed  movsx   rsi, r9w
0x180007af1  mov     rbp, r8
0x180007af4  mov     r14d, edx
0x180007af7  mov     r15, rcx
0x180007afa  test    r8, r8
0x180007afd  jz      loc_180007BD3
0x180007b03  lea     eax, [rsi+30h]
0x180007b06  movzx   ebx, ax
0x180007b09  call    cs:__imp_GetProcessHeap
0x180007b0f  mov     r8d, ebx; dwBytes
0x180007b12  mov     ebx, 8
0x180007b17  mov     edx, ebx; dwFlags
0x180007b19  mov     rcx, rax; hHeap
0x180007b1c  call    cs:__imp_HeapAlloc
0x180007b22  mov     rdi, rax
0x180007b25  test    rax, rax
0x180007b28  jz      loc_180007BFB
0x180007b2e  mov     [rax+28h], r14d
0x180007b32  mov     ecx, 200h
0x180007b37  lea     eax, [rbx+rsi]
0x180007b3a  mov     [rdi], ax
0x180007b3d  add     ax, 28h ; '('
0x180007b41  mov     [rdi+2], ax
0x180007b45  cmp     ax, cx
0x180007b48  jg      loc_180007C0A
0x180007b4e  mov     r8, rsi; Size
0x180007b51  lea     rcx, [rdi+30h]; void *
0x180007b55  mov     rdx, rbp; Src
0x180007b58  call    memcpy_0
0x180007b5d  mov     rcx, [r15+10h]
0x180007b61  xor     r9d, r9d
0x180007b64  mov     [rsp+78h+var_40], 0
0x180007b6d  mov     r8, rdi
0x180007b70  mov     [rsp+78h+var_48], 0
0x180007b79  mov     edx, 10000h
0x180007b7e  mov     [rsp+78h+var_50], 0; void *
0x180007b87  mov     qword ptr [rsp+78h+var_58], 0
0x180007b90  call    cs:__imp_NtAlpcSendWaitReceivePort
0x180007b96  mov     ebx, eax
0x180007b98  mov     rcx, r15; this
0x180007b9b  bts     ebx, 1Ch
0x180007b9f  mov     r9d, eax
0x180007ba2  mov     edx, ebx; int
0x180007ba4  call    ?CheckHRESULT@CPortClient@@AEAAJJ@Z; CPortClient::CheckHRESULT(long)
0x180007ba9  test    r9d, r9d
0x180007bac  js      short loc_180007C1F
0x180007bae  xor     ebx, ebx
0x180007bb0  call    cs:__imp_GetProcessHeap
0x180007bb6  mov     r8, rdi; lpMem
0x180007bb9  xor     edx, edx; dwFlags
0x180007bbb  mov     rcx, rax; hHeap
0x180007bbe  call    cs:__imp_HeapFree
0x180007bc4  mov     eax, ebx
0x180007bc6  add     rsp, 48h
0x180007bca  pop     r15
0x180007bcc  pop     r14
0x180007bce  pop     rdi
0x180007bcf  pop     rsi
0x180007bd0  pop     rbp
0x180007bd1  pop     rbx
0x180007bd2  retn
0x180007bd3  mov     ebx, 80070006h
0x180007bd8  mov     [rsp+78h+var_58], 188h; unsigned int
0x180007be0  mov     r8d, 9; unsigned int
0x180007be6  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@CPortClient@@2QBJB; int *
0x180007bed  mov     r9d, ebx; int
0x180007bf0  lea     ecx, [r8-5]; unsigned int
0x180007bf4  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180007bf9  jmp     short loc_180007BC4
0x180007bfb  mov     ebx, 8007000Eh
0x180007c00  mov     [rsp+78h+var_58], 18Bh
0x180007c08  jmp     short loc_180007BE0
0x180007c0a  mov     rcx, [rsp+78h]; this
0x180007c0f  mov     r9d, 8007029Ch; char *
0x180007c15  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180007c1a  jmp     loc_180007B4E
0x180007c1f  mov     r8d, 9; unsigned int
0x180007c25  mov     [rsp+78h+var_58], 19Ch; unsigned int
0x180007c2d  mov     r9d, ebx; int
0x180007c30  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@CPortClient@@2QBJB; int *
0x180007c37  lea     ecx, [r8-5]; unsigned int
0x180007c3b  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180007c40  jmp     loc_180007BB0
```
