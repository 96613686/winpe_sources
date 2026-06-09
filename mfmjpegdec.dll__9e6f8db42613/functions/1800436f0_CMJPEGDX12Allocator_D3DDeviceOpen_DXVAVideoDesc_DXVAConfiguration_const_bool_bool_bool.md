# CMJPEGDX12Allocator::D3DDeviceOpen(DXVAVideoDesc &,DXVAConfiguration const &,bool,bool,bool)

- ea: `0x1800436f0`
- end: `0x180043828`
- name: `?D3DDeviceOpen@CMJPEGDX12Allocator@@UEAAJAEAUDXVAVideoDesc@@AEBUDXVAConfiguration@@_N22@Z`
- size: `312`
- prototype: `int(CMJPEGDX12Allocator *__hidden this, struct DXVAVideoDesc *, const struct DXVAConfiguration *, bool, bool, bool)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180024220`
- `0x180024bf4`
- `0x1800436f0`
- `0x1800499c0`
- `0x180054780`
- `0x18006ef8f`
- `0x180070010`

## pseudocode

```c
int __fastcall CMJPEGDX12Allocator::D3DDeviceOpen(
        CDXVAFrameManagerGenericDecode **this,
        struct DXVAVideoDesc *a2,
        const struct DXVAConfiguration *a3,
        unsigned __int8 a4,
        bool a5)
{
  int v6; // esi
  const void *v8; // rax
  int result; // eax
  struct CDXVABufferTracker *v10; // [rsp+30h] [rbp-D8h] BYREF
  unsigned int v11; // [rsp+38h] [rbp-D0h] BYREF
  _BYTE v12[16]; // [rsp+40h] [rbp-C8h] BYREF
  int v13; // [rsp+50h] [rbp-B8h]
  int v14; // [rsp+70h] [rbp-98h]
  int v15; // [rsp+80h] [rbp-88h]
  int v16; // [rsp+90h] [rbp-78h]
  _BYTE v17[56]; // [rsp+C0h] [rbp-48h] BYREF

  v6 = a4;
  v10 = 0;
  memset_0(v12, 0, 0x80u);
  v13 = 64;
  v15 = 512;
  v16 = 2176;
  if ( a5
    || (v8 = (const void *)(*((__int64 (__fastcall **)(CDXVAFrameManagerGenericDecode **, _BYTE *))*this + 53))(
                             this,
                             v17),
        (result = memcmp_0(a2, v8, 0x34u)) != 0) )
  {
    v14 = (int)((double)(*(_DWORD *)a2 * *((_DWORD *)a2 + 1) + 1) * 1.8);
    result = CDX12DecodeCore::D3DDeviceOpen(
               (CDX12DecodeCore *)(this + 13),
               a2,
               (const struct DXVAParams_tag *)v12,
               &v11,
               v6,
               &v10);
    if ( result >= 0 )
    {
      result = CDXVAFrameManagerGenericDecode::SetNewOutputSamples(
                 this[12],
                 v10,
                 *((_DWORD *)a2 + 8),
                 0,
                 *(_DWORD *)a2,
                 *((_DWORD *)a2 + 1));
      if ( result >= 0 )
        *((_BYTE *)this + 8) = 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800436f0  mov     [rsp+arg_10], rbx
0x1800436f5  mov     [rsp+arg_18], rsi
0x1800436fa  push    rdi
0x1800436fb  sub     rsp, 100h
0x180043702  mov     rax, cs:__security_cookie
0x180043709  xor     rax, rsp
0x18004370c  mov     [rsp+108h+var_10], rax
0x180043714  mov     rbx, rdx
0x180043717  movzx   esi, r9b
0x18004371b  mov     rdi, rcx
0x18004371e  mov     [rsp+108h+var_D8], 0
0x180043727  xor     edx, edx; Val
0x180043729  lea     rcx, [rsp+108h+var_C8]; void *
0x18004372e  mov     r8d, 80h; Size
0x180043734  call    memset_0
0x180043739  cmp     [rsp+108h+arg_20], 0
0x180043741  mov     [rsp+108h+var_B8], 40h ; '@'
0x180043749  mov     [rsp+108h+var_88], 200h
0x180043754  mov     [rsp+108h+var_78], 880h
0x18004375f  jnz     short loc_180043790
0x180043761  mov     rax, [rdi]
0x180043764  lea     rdx, [rsp+108h+var_48]
0x18004376c  mov     rcx, rdi
0x18004376f  mov     rax, [rax+1A8h]
0x180043776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004377b  mov     r8d, 34h ; '4'; Size
0x180043781  mov     rdx, rax; Buf2
0x180043784  mov     rcx, rbx; Buf1
0x180043787  call    memcmp_0
0x18004378c  test    eax, eax
0x18004378e  jz      short loc_180043803
0x180043790  mov     eax, [rbx+4]
0x180043793  lea     rdx, [rsp+108h+var_D8]
0x180043798  imul    eax, [rbx]
0x18004379b  lea     rcx, [rdi+68h]; this
0x18004379f  xorps   xmm0, xmm0
0x1800437a2  mov     [rsp+108h+var_E0], rdx; struct CDXVABufferTracker **
0x1800437a7  lea     r9, [rsp+108h+var_D0]; unsigned int *
0x1800437ac  mov     [rsp+108h+var_E8], esi; int
0x1800437b0  lea     r8, [rsp+108h+var_C8]; struct DXVAParams_tag *
0x1800437b5  mov     rdx, rbx; struct DXVAVideoDesc *
0x1800437b8  inc     eax
0x1800437ba  cvtsi2sd xmm0, rax
0x1800437bf  mulsd   xmm0, cs:__real@3ffccccccccccccd
0x1800437c7  cvttsd2si rax, xmm0
0x1800437cc  mov     [rsp+108h+var_98], eax
0x1800437d0  call    ?D3DDeviceOpen@CDX12DecodeCore@@UEAAJAEBUDXVAVideoDesc@@PEBUDXVAParams_tag@@AEAKHPEAPEAVCDXVABufferTracker@@@Z; CDX12DecodeCore::D3DDeviceOpen(DXVAVideoDesc const &,DXVAParams_tag const *,ulong &,int,CDXVABufferTracker * *)
0x1800437d5  test    eax, eax
0x1800437d7  js      short loc_180043803
0x1800437d9  mov     eax, [rbx+4]
0x1800437dc  xor     r9d, r9d; unsigned __int8
0x1800437df  mov     r8d, [rbx+20h]; unsigned int
0x1800437e3  mov     rdx, [rsp+108h+var_D8]; struct CDXVABufferTracker *
0x1800437e8  mov     rcx, [rdi+60h]; this
0x1800437ec  mov     dword ptr [rsp+108h+var_E0], eax; unsigned int
0x1800437f0  mov     eax, [rbx]
0x1800437f2  mov     [rsp+108h+var_E8], eax; unsigned int
0x1800437f6  call    ?SetNewOutputSamples@CDXVAFrameManagerGenericDecode@@UEAAJPEAVCDXVABufferTracker@@KEII@Z; CDXVAFrameManagerGenericDecode::SetNewOutputSamples(CDXVABufferTracker *,ulong,uchar,uint,uint)
0x1800437fb  test    eax, eax
0x1800437fd  js      short loc_180043803
0x1800437ff  mov     byte ptr [rdi+8], 1
0x180043803  mov     rcx, [rsp+108h+var_10]
0x18004380b  xor     rcx, rsp; StackCookie
0x18004380e  call    __security_check_cookie
0x180043813  lea     r11, [rsp+108h+var_8]
0x18004381b  mov     rbx, [r11+20h]
0x18004381f  mov     rsi, [r11+28h]
0x180043823  mov     rsp, r11
0x180043826  pop     rdi
0x180043827  retn
```
