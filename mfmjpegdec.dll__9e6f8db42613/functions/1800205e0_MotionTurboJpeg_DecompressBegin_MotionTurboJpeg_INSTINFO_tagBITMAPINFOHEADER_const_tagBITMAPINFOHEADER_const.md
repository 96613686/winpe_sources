# MotionTurboJpeg::DecompressBegin(MotionTurboJpeg::INSTINFO *,tagBITMAPINFOHEADER * const,tagBITMAPINFOHEADER * const)

- ea: `0x1800205e0`
- end: `0x1800206f4`
- name: `?DecompressBegin@MotionTurboJpeg@@YAKPEAUINSTINFO@1@QEAUtagBITMAPINFOHEADER@@1@Z`
- size: `276`
- prototype: `unsigned int __fastcall(MotionTurboJpeg *this, struct MotionTurboJpeg::INSTINFO *, struct tagBITMAPINFOHEADER *const, struct tagBITMAPINFOHEADER *const)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001ff0c`

## callees

- `0x18001bb44`
- `0x18001ea94`
- `0x1800205e0`
- `0x180020e4c`
- `0x180024bf4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned int __fastcall MotionTurboJpeg::DecompressBegin(
        MotionTurboJpeg *this,
        struct MotionTurboJpeg::INSTINFO *a2,
        struct tagBITMAPINFOHEADER *const a3,
        struct tagBITMAPINFOHEADER *const a4)
{
  unsigned int result; // eax
  int v8; // eax

  if ( *((_BYTE *)this + 6864) == 1 )
  {
    MotionTurboJpeg::DecompressEnd(this, a2);
    *((_BYTE *)this + 6864) = 0;
  }
  result = MotionTurboJpeg::DecompressQuery(this, a2, (const struct MotionTurboJpeg::tagJPEGEXBMINFOHEADER *)a3, a4);
  if ( !result )
  {
    memset_0((char *)this + 8, 0, 0xA8u);
    *((_QWORD *)this + 1) = error_exit;
    *((_QWORD *)this + 2) = emit_message;
    *((_QWORD *)this + 3) = output_message;
    *((_QWORD *)this + 4) = &format_message;
    *((_QWORD *)this + 5) = reset_error_mgr;
    *((_QWORD *)this + 18) = off_180071030;
    *((_DWORD *)this + 38) = 129;
    *((_QWORD *)this + 22) = (char *)this + 8;
    jpeg_CreateDecompress();
    *((_BYTE *)this + 6864) = 1;
    v8 = 844715353;
    if ( a3->biCompression == 844715353 )
    {
      *((_DWORD *)this + 435) = 2;
    }
    else
    {
      v8 = 842094158;
      if ( a3->biCompression == 842094158 )
      {
        *((_DWORD *)this + 435) = 1;
      }
      else
      {
        v8 = 1448433985;
        if ( a3->biCompression != 1448433985 )
        {
LABEL_11:
          *(_DWORD *)this = *((_DWORD *)a2 + 4);
          return 0;
        }
        *((_DWORD *)this + 435) = 4;
      }
    }
    *((_DWORD *)this + 436) = v8;
    goto LABEL_11;
  }
  return result;
}

```

## disassembly

```asm
0x1800205e0  push    rbx
0x1800205e2  push    rsi
0x1800205e3  push    rdi
0x1800205e4  push    r14
0x1800205e6  sub     rsp, 28h
0x1800205ea  mov     r14, r8
0x1800205ed  mov     rsi, rdx
0x1800205f0  mov     rdi, rcx
0x1800205f3  cmp     byte ptr [rcx+1AD0h], 1
0x1800205fa  jnz     short loc_180020608
0x1800205fc  call    ?DecompressEnd@MotionTurboJpeg@@YAKPEAUINSTINFO@1@@Z; MotionTurboJpeg::DecompressEnd(MotionTurboJpeg::INSTINFO *)
0x180020601  mov     byte ptr [rdi+1AD0h], 0
0x180020608  mov     r8, r14; struct MotionTurboJpeg::tagJPEGEXBMINFOHEADER *
0x18002060b  mov     rdx, rsi; struct MotionTurboJpeg::INSTINFO *
0x18002060e  call    ?DecompressQuery@MotionTurboJpeg@@YAKPEAUINSTINFO@1@PEBUtagJPEGEXBMINFOHEADER@1@QEAUtagBITMAPINFOHEADER@@@Z; MotionTurboJpeg::DecompressQuery(MotionTurboJpeg::INSTINFO *,MotionTurboJpeg::tagJPEGEXBMINFOHEADER const *,tagBITMAPINFOHEADER * const)
0x180020613  test    eax, eax
0x180020615  jnz     loc_1800206EA
0x18002061b  lea     rbx, [rdi+8]
0x18002061f  xor     edx, edx; Val
0x180020621  mov     r8d, 0A8h; Size
0x180020627  mov     rcx, rbx; void *
0x18002062a  call    memset_0
0x18002062f  lea     rax, error_exit
0x180020636  mov     [rbx], rax
0x180020639  lea     rax, emit_message
0x180020640  mov     [rbx+8], rax
0x180020644  lea     rax, output_message
0x18002064b  mov     [rbx+10h], rax
0x18002064f  lea     rax, format_message
0x180020656  mov     [rbx+18h], rax
0x18002065a  lea     rax, reset_error_mgr
0x180020661  mov     [rbx+20h], rax
0x180020665  lea     rax, off_180071030; "Bogus message code %d"
0x18002066c  mov     [rbx+88h], rax
0x180020673  mov     dword ptr [rbx+90h], 81h
0x18002067d  lea     rcx, [rdi+0B0h]
0x180020684  mov     [rcx], rbx
0x180020687  call    jpeg_CreateDecompress
0x18002068c  mov     byte ptr [rdi+1AD0h], 1
0x180020693  mov     eax, 32595559h
0x180020698  cmp     [r14+10h], eax
0x18002069c  jnz     short loc_1800206AA
0x18002069e  mov     dword ptr [rdi+6CCh], 2
0x1800206a8  jmp     short loc_1800206D6
0x1800206aa  mov     eax, 3231564Eh
0x1800206af  cmp     [r14+10h], eax
0x1800206b3  jnz     short loc_1800206C1
0x1800206b5  mov     dword ptr [rdi+6CCh], 1
0x1800206bf  jmp     short loc_1800206D6
0x1800206c1  mov     eax, 56555941h
0x1800206c6  cmp     [r14+10h], eax
0x1800206ca  jnz     short loc_1800206DC
0x1800206cc  mov     dword ptr [rdi+6CCh], 4
0x1800206d6  mov     [rdi+6D0h], eax
0x1800206dc  mov     eax, [rsi+10h]
0x1800206df  mov     [rdi], eax
0x1800206e1  xor     eax, eax
0x1800206e3  jmp     short loc_1800206EA
0x1800206e5  mov     eax, 0FFFFFFFDh
0x1800206ea  add     rsp, 28h
0x1800206ee  pop     r14
0x1800206f0  pop     rdi
0x1800206f1  pop     rsi
0x1800206f2  pop     rbx
0x1800206f3  retn
```
