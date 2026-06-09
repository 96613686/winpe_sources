# dxc::CAnalysisSinkImpl::SetPrimitiveBlend(D2D1_PRIMITIVE_BLEND)

- ea: `0x1802a0e00`
- end: `0x1802a0e96`
- name: `?SetPrimitiveBlend@CAnalysisSinkImpl@dxc@@UEAAJW4D2D1_PRIMITIVE_BLEND@@@Z`
- size: `150`
- prototype: `__int64 __fastcall(dxc::CAnalysisSinkImpl *__hidden this, enum D2D1_PRIMITIVE_BLEND)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1801f7fbc`
- `0x1802a0e00`
- `0x1802a7d1c`

## import_xrefs

- `ntdll!WinSqmIncrementDWORD` at `0x1802a0e4b`
- `ntdll!WinSqmIncrementDWORD` at `0x1802a0e4b`

## string_xrefs

- `0x1802a0e37`: `Use of complex primitive blend mode`
- `0x1802a0e51`: `Use of D2D1_PRIMITIVE_BLEND_COPY`

## pseudocode

```c
__int64 __fastcall dxc::CAnalysisSinkImpl::SetPrimitiveBlend(
        dxc::CAnalysisSinkImpl *this,
        enum D2D1_PRIMITIVE_BLEND a2)
{
  dxc **v2; // rsi
  unsigned int v5; // ebp
  const wchar_t *v6; // r8
  int v7; // eax

  v2 = (dxc **)((char *)this + 16);
  if ( *((_DWORD *)this + 2) != 8 )
    dxc::ActionRecorder::RecordCall((char *)*v2 + 408, 7);
  v5 = 0;
  if ( a2 )
  {
    if ( a2 == D2D1_PRIMITIVE_BLEND_COPY )
    {
      WinSqmIncrementDWORD(0, 8096, 1);
      v6 = (const wchar_t *)L"Use of D2D1_PRIMITIVE_BLEND_COPY";
    }
    else
    {
      v6 = L"Use of complex primitive blend mode";
    }
    *((_DWORD *)this + 3) |= 0x10u;
    dxc::OutputDebugMessage(*v2, (const struct dxc::RenderState *)0x4CB, (unsigned int)v6);
  }
  else
  {
    *((_DWORD *)this + 3) &= ~0x10u;
  }
  v7 = *((_DWORD *)this + 3);
  if ( (v7 & 8) != 0 && ((v7 & 4) != 0 || *((_DWORD *)this + 2) == 8) )
  {
    v5 = -2142108160;
    *((_DWORD *)this + 3) = v7 | 2;
  }
  return v5;
}

```

## disassembly

```asm
0x1802a0e00  push    rbx
0x1802a0e02  push    rbp
0x1802a0e03  push    rsi
0x1802a0e04  push    rdi
0x1802a0e05  sub     rsp, 28h
0x1802a0e09  cmp     dword ptr [rcx+8], 8
0x1802a0e0d  lea     rsi, [rcx+10h]
0x1802a0e11  mov     edi, edx
0x1802a0e13  mov     rbx, rcx
0x1802a0e16  jz      short loc_1802A0E2C
0x1802a0e18  mov     rcx, [rsi]
0x1802a0e1b  mov     edx, 7
0x1802a0e20  add     rcx, 198h
0x1802a0e27  call    ?RecordCall@ActionRecorder@dxc@@QEAA_KW4EMethodId@2@@Z; dxc::ActionRecorder::RecordCall(dxc::EMethodId)
0x1802a0e2c  xor     ebp, ebp
0x1802a0e2e  test    edi, edi
0x1802a0e30  jz      short loc_1802A0E6B
0x1802a0e32  cmp     edi, 1
0x1802a0e35  jz      short loc_1802A0E40
0x1802a0e37  lea     r8, aUseOfComplexPr; "Use of complex primitive blend mode"
0x1802a0e3e  jmp     short loc_1802A0E58
0x1802a0e40  xor     ecx, ecx
0x1802a0e42  mov     edx, 1FA0h
0x1802a0e47  lea     r8d, [rcx+1]
0x1802a0e4b  call    cs:__imp_WinSqmIncrementDWORD
0x1802a0e51  lea     r8, aUseOfD2d1Primi; "Use of D2D1_PRIMITIVE_BLEND_COPY"
0x1802a0e58  or      dword ptr [rbx+0Ch], 10h
0x1802a0e5c  mov     edx, 4CBh; struct dxc::RenderState *
0x1802a0e61  mov     rcx, [rsi]; this
0x1802a0e64  call    ?OutputDebugMessage@dxc@@YAXPEBURenderState@1@IZZ; dxc::OutputDebugMessage(dxc::RenderState const *,uint,...)
0x1802a0e69  jmp     short loc_1802A0E6F
0x1802a0e6b  and     dword ptr [rbx+0Ch], 0FFFFFFEFh
0x1802a0e6f  mov     eax, [rbx+0Ch]
0x1802a0e72  test    al, 8
0x1802a0e74  jz      short loc_1802A0E8B
0x1802a0e76  test    al, 4
0x1802a0e78  jnz     short loc_1802A0E80
0x1802a0e7a  cmp     dword ptr [rbx+8], 8
0x1802a0e7e  jnz     short loc_1802A0E8B
0x1802a0e80  or      eax, 2
0x1802a0e83  mov     ebp, 80520600h
0x1802a0e88  mov     [rbx+0Ch], eax
0x1802a0e8b  mov     eax, ebp
0x1802a0e8d  add     rsp, 28h
0x1802a0e91  pop     rdi
0x1802a0e92  pop     rsi
0x1802a0e93  pop     rbp
0x1802a0e94  pop     rbx
0x1802a0e95  retn
```
