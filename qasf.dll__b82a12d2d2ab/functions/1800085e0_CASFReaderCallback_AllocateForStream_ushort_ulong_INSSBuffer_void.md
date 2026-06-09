# CASFReaderCallback::AllocateForStream(ushort,ulong,INSSBuffer * *,void *)

- ea: `0x1800085e0`
- end: `0x18000875e`
- name: `?AllocateForStream@CASFReaderCallback@@UEAAJGKPEAPEAUINSSBuffer@@PEAX@Z`
- size: `382`
- prototype: `__int64 __fastcall(CASFReaderCallback *this, unsigned __int16, unsigned int, struct INSSBuffer **)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001020`
- `0x180001460`
- `0x180007e14`
- `0x1800085e0`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReaderCallback::AllocateForStream(
        CASFReaderCallback *this,
        unsigned __int16 a2,
        unsigned int a3,
        struct INSSBuffer **a4)
{
  __int64 v4; // rcx
  __int64 v8; // rcx
  int v9; // r8d
  __int64 v10; // rdx
  int v11; // ebx
  bool v12; // sf
  struct IMediaSampleVtbl *lpVtbl; // rax
  CWMReadSample *v14; // rax
  struct INSSBuffer *v15; // rax
  struct IMediaSample *v16; // [rsp+30h] [rbp-28h] BYREF

  v4 = *((_QWORD *)this + 1);
  if ( *(_DWORD *)(v4 + 448) )
    return 2147500033LL;
  v8 = *(_QWORD *)(v4 + 280);
  if ( v8 )
  {
    v9 = a2;
    do
    {
      v10 = *(_QWORD *)(v8 + 16);
      if ( *(_DWORD *)(v10 + 304) == v9 )
        break;
      v8 = *(_QWORD *)(v8 + 8);
    }
    while ( v8 );
    if ( *(_QWORD *)(v10 + 48) )
    {
      v16 = 0;
      v11 = (*(__int64 (__fastcall **)(_QWORD, struct IMediaSample **, _QWORD, _QWORD, _DWORD))(**(_QWORD **)(v10 + 216)
                                                                                              + 56LL))(
              *(_QWORD *)(v10 + 216),
              &v16,
              0,
              0,
              0);
      if ( v11 < 0 )
        return (unsigned int)v11;
      v12 = ((int (__fastcall *)(struct IMediaSample *))v16->lpVtbl->GetSize)(v16) < 0;
      lpVtbl = v16->lpVtbl;
      if ( v12 )
      {
LABEL_12:
        ((void (*)(void))lpVtbl->Release)();
        return 2147549183LL;
      }
      ((void (*)(void))lpVtbl->GetSize)();
      if ( ((unsigned int (__fastcall *)(struct IMediaSample *))v16->lpVtbl->GetSize)(v16) < a3 )
      {
        lpVtbl = v16->lpVtbl;
        goto LABEL_12;
      }
      v14 = (CWMReadSample *)operator new(0x50u);
      if ( v14 )
      {
        v15 = (struct INSSBuffer *)CWMReadSample::CWMReadSample(v14, v16);
        *a4 = v15;
        if ( v15 )
        {
          ((void (__fastcall *)(struct INSSBuffer *))v15->lpVtbl->AddRef)(v15);
          ((void (__fastcall *)(struct IMediaSample *, _QWORD))v16->lpVtbl->SetActualDataLength)(v16, a3);
LABEL_18:
          ((void (__fastcall *)(struct IMediaSample *))v16->lpVtbl->Release)(v16);
          return (unsigned int)v11;
        }
      }
      else
      {
        *a4 = 0;
      }
      v11 = -2147024882;
      goto LABEL_18;
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800085e0  push    rbx
0x1800085e2  push    rsi
0x1800085e3  push    rdi
0x1800085e4  sub     rsp, 40h
0x1800085e8  mov     rax, cs:__security_cookie
0x1800085ef  xor     rax, rsp
0x1800085f2  mov     [rsp+58h+var_20], rax
0x1800085f7  mov     rcx, [rcx+8]
0x1800085fb  mov     rdi, r9
0x1800085fe  mov     esi, r8d
0x180008601  cmp     dword ptr [rcx+1C0h], 0
0x180008608  jz      short loc_180008614
0x18000860a  mov     eax, 80004001h
0x18000860f  jmp     loc_180008749
0x180008614  mov     rcx, [rcx+118h]
0x18000861b  test    rcx, rcx
0x18000861e  jz      loc_180008744
0x180008624  movzx   r8d, dx
0x180008628  mov     rdx, [rcx+10h]
0x18000862c  cmp     [rdx+130h], r8d
0x180008633  jz      short loc_180008641
0x180008635  mov     rax, [rcx+8]
0x180008639  mov     rcx, rax
0x18000863c  test    rax, rax
0x18000863f  jnz     short loc_180008628
0x180008641  cmp     qword ptr [rdx+30h], 0
0x180008646  jz      loc_180008744
0x18000864c  mov     [rsp+58h+var_28], 0
0x180008655  xor     r9d, r9d
0x180008658  mov     rcx, [rdx+0D8h]
0x18000865f  xor     r8d, r8d
0x180008662  lea     rdx, [rsp+58h+var_28]
0x180008667  mov     [rsp+58h+var_38], 0
0x18000866f  mov     rax, [rcx]
0x180008672  mov     rax, [rax+38h]
0x180008676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000867b  mov     ebx, eax
0x18000867d  test    eax, eax
0x18000867f  js      loc_180008740
0x180008685  mov     rcx, [rsp+58h+var_28]
0x18000868a  mov     rdx, [rcx]
0x18000868d  mov     rax, [rdx+20h]
0x180008691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008696  mov     rcx, [rsp+58h+var_28]
0x18000869b  test    eax, eax
0x18000869d  mov     rax, [rcx]
0x1800086a0  js      short loc_1800086C8
0x1800086a2  mov     rax, [rax+20h]
0x1800086a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086ab  mov     rcx, [rsp+58h+var_28]
0x1800086b0  mov     rax, [rcx]
0x1800086b3  mov     rax, [rax+20h]
0x1800086b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086bc  cmp     eax, esi
0x1800086be  jnb     short loc_1800086D8
0x1800086c0  mov     rcx, [rsp+58h+var_28]
0x1800086c5  mov     rax, [rcx]
0x1800086c8  mov     rax, [rax+10h]
0x1800086cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086d1  mov     eax, 8000FFFFh
0x1800086d6  jmp     short loc_180008749
0x1800086d8  mov     ecx, 50h ; 'P'; Size
0x1800086dd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800086e2  test    rax, rax
0x1800086e5  jz      short loc_180008723
0x1800086e7  mov     rdx, [rsp+58h+var_28]; struct IMediaSample *
0x1800086ec  mov     rcx, rax; this
0x1800086ef  call    ??0CWMReadSample@@QEAA@PEAUIMediaSample@@@Z; CWMReadSample::CWMReadSample(IMediaSample *)
0x1800086f4  mov     [rdi], rax
0x1800086f7  mov     r8, rax
0x1800086fa  test    rax, rax
0x1800086fd  jz      short loc_18000872A
0x1800086ff  mov     rcx, [rax]
0x180008702  mov     rax, [rcx+8]
0x180008706  mov     rcx, r8
0x180008709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000870e  mov     rcx, [rsp+58h+var_28]
0x180008713  mov     edx, esi
0x180008715  mov     rax, [rcx]
0x180008718  mov     rax, [rax+60h]
0x18000871c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008721  jmp     short loc_18000872F
0x180008723  mov     qword ptr [rdi], 0
0x18000872a  mov     ebx, 8007000Eh
0x18000872f  mov     rcx, [rsp+58h+var_28]
0x180008734  mov     rax, [rcx]
0x180008737  mov     rax, [rax+10h]
0x18000873b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008740  mov     eax, ebx
0x180008742  jmp     short loc_180008749
0x180008744  mov     eax, 80004005h
0x180008749  mov     rcx, [rsp+58h+var_20]
0x18000874e  xor     rcx, rsp; StackCookie
0x180008751  call    __security_check_cookie
0x180008756  add     rsp, 40h
0x18000875a  pop     rdi
0x18000875b  pop     rsi
0x18000875c  pop     rbx
0x18000875d  retn
```
