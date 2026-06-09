# CBodyLockBytes::HrHandsOffStorage(void)

- ea: `0x180019494`
- end: `0x180019594`
- name: `?HrHandsOffStorage@CBodyLockBytes@@QEAAJXZ`
- size: `256`
- prototype: `__int64 __fastcall(CBodyLockBytes *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180019398`

## callees

- `0x180002098`
- `0x180019494`
- `0x18001dfe4`
- `0x180021140`
- `0x1800299d0`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!HrCopyLockBytesToStream` at `0x1800194f2`
- `MSOERT2!HrCopyLockBytesToStream` at `0x1800194f2`
- `SHLWAPI!__imp_IStream_Reset` at `0x180019528`
- `SHLWAPI!__imp_IStream_Reset` at `0x180019528`
- `KERNEL32!LeaveCriticalSection` at `0x180019583`
- `KERNEL32!LeaveCriticalSection` at `0x180019583`
- `KERNEL32!EnterCriticalSection` at `0x1800194ab`
- `KERNEL32!EnterCriticalSection` at `0x1800194ab`

## pseudocode

```c
__int64 __fastcall CBodyLockBytes::HrHandsOffStorage(CBodyLockBytes *this)
{
  HRESULT v2; // edi
  bool v3; // cc
  int v4; // eax
  IStream *v5; // rsi
  CStreamLockBytes *v6; // rax
  CStreamLockBytes *v7; // rax
  IStream *pstm; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  pstm = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( !*((_DWORD *)this + 3) )
    goto LABEL_14;
  if ( *((_DWORD *)this + 4) )
    goto LABEL_14;
  v3 = *((_DWORD *)this + 2) <= 1;
  *((_DWORD *)this + 3) = 0;
  if ( v3 )
    goto LABEL_14;
  v4 = MimeOleCreateVirtualStream(&pstm);
  v5 = pstm;
  v2 = v4;
  if ( v4 >= 0 )
  {
    v2 = HrCopyLockBytesToStream(this, pstm, 0);
    if ( v2 >= 0 )
    {
      *((_QWORD *)this + 4) -= *((_QWORD *)this + 3);
      *((_QWORD *)this + 3) = 0;
      v2 = ((__int64 (__fastcall *)(IStream *, _QWORD))v5->lpVtbl->Commit)(v5, 0);
      if ( v2 >= 0 )
      {
        v2 = IStream_Reset(v5);
        OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>((char *)this + 40);
        v6 = (CStreamLockBytes *)operator new(0x48u);
        if ( v6 )
        {
          v7 = CStreamLockBytes::CStreamLockBytes(v6, v5);
          *((_QWORD *)this + 5) = v7;
          if ( v7 )
            goto LABEL_12;
        }
        else
        {
          *((_QWORD *)this + 5) = 0;
        }
        v2 = -2147024882;
      }
    }
  }
LABEL_12:
  if ( v5 )
    ((void (__fastcall *)(IStream *))v5->lpVtbl->Release)(v5);
LABEL_14:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180019494  push    rbx
0x180019496  push    rbp
0x180019497  push    rsi
0x180019498  push    rdi
0x180019499  sub     rsp, 28h
0x18001949d  mov     rbx, rcx
0x1800194a0  xor     edi, edi
0x1800194a2  add     rcx, 30h ; '0'; lpCriticalSection
0x1800194a6  mov     [rsp+48h+pstm], rdi
0x1800194ab  call    cs:__imp_EnterCriticalSection
0x1800194b1  cmp     [rbx+0Ch], edi
0x1800194b4  jz      loc_18001957F
0x1800194ba  cmp     [rbx+10h], edi
0x1800194bd  jnz     loc_18001957F
0x1800194c3  cmp     dword ptr [rbx+8], 1
0x1800194c7  mov     [rbx+0Ch], edi
0x1800194ca  jle     loc_18001957F
0x1800194d0  lea     rcx, [rsp+48h+pstm]
0x1800194d5  call    MimeOleCreateVirtualStream
0x1800194da  mov     rsi, [rsp+48h+pstm]
0x1800194df  mov     edi, eax
0x1800194e1  test    eax, eax
0x1800194e3  js      loc_18001956B
0x1800194e9  xor     r8d, r8d
0x1800194ec  mov     rdx, rsi
0x1800194ef  mov     rcx, rbx
0x1800194f2  call    cs:__imp_HrCopyLockBytesToStream
0x1800194f8  mov     edi, eax
0x1800194fa  test    eax, eax
0x1800194fc  js      short loc_18001956B
0x1800194fe  mov     rax, [rbx+18h]
0x180019502  xor     edx, edx
0x180019504  sub     [rbx+20h], rax
0x180019508  mov     rcx, rsi
0x18001950b  mov     qword ptr [rbx+18h], 0
0x180019513  mov     rax, [rsi]
0x180019516  mov     rax, [rax+40h]
0x18001951a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001951f  mov     edi, eax
0x180019521  test    eax, eax
0x180019523  js      short loc_18001956B
0x180019525  mov     rcx, rsi; pstm
0x180019528  call    cs:__imp_IStream_Reset
0x18001952e  lea     rcx, [rbx+28h]
0x180019532  mov     edi, eax
0x180019534  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180019539  mov     ecx, 48h ; 'H'; Size
0x18001953e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019543  test    rax, rax
0x180019546  jz      short loc_18001955E
0x180019548  mov     rdx, rsi; struct IStream *
0x18001954b  mov     rcx, rax; this
0x18001954e  call    ??0CStreamLockBytes@@QEAA@PEAUIStream@@@Z; CStreamLockBytes::CStreamLockBytes(IStream *)
0x180019553  mov     [rbx+28h], rax
0x180019557  test    rax, rax
0x18001955a  jz      short loc_180019566
0x18001955c  jmp     short loc_18001956B
0x18001955e  mov     qword ptr [rbx+28h], 0
0x180019566  mov     edi, 8007000Eh
0x18001956b  test    rsi, rsi
0x18001956e  jz      short loc_18001957F
0x180019570  mov     rax, [rsi]
0x180019573  mov     rcx, rsi
0x180019576  mov     rax, [rax+10h]
0x18001957a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001957f  lea     rcx, [rbx+30h]; lpCriticalSection
0x180019583  call    cs:__imp_LeaveCriticalSection
0x180019589  mov     eax, edi
0x18001958b  add     rsp, 28h
0x18001958f  pop     rdi
0x180019590  pop     rsi
0x180019591  pop     rbp
0x180019592  pop     rbx
0x180019593  retn
```
