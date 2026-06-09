# PolyPatBlt

- ea: `0x18007abf0`
- end: `0x18007afdd`
- name: `PolyPatBlt`
- size: `1005`
- prototype: `__int64 __usercall@<rax>(HDC hdc@<rcx>, DWORD rop@<edx>, void *Src@<r8>, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800756cc`
- `0x18007a830`
- `0x18007abf0`
- `0x1800a6370`
- `0x1800a68d4`

## import_xrefs

- `GDI32!SelectObject` at `0x18007af55`
- `GDI32!SelectObject` at `0x18007af73`
- `GDI32!SelectObject` at `0x18007afbc`
- `GDI32!SelectObject` at `0x18007af55`
- `GDI32!SelectObject` at `0x18007af73`
- `GDI32!SelectObject` at `0x18007afbc`
- `GDI32!GdiGetEntry` at `0x18007ac3b`
- `GDI32!GdiGetEntry` at `0x18007ac3b`
- `GDI32!GdiBatchLimit` at `0x18007aeed`
- `GDI32!gW32PID` at `0x18007ac6d`
- `GDI32!gCookie` at `0x18007ac89`
- `GDI32!gMaxGdiHandleCount` at `0x18007ac1c`
- `USER32!IsThreadDesktopComposited` at `0x18007ad24`
- `USER32!IsThreadDesktopComposited` at `0x18007ad24`
- `win32u!NtGdiFlush` at `0x18007af08`
- `win32u!NtGdiFlush` at `0x18007af08`
- `win32u!NtGdiPolyPatBlt` at `0x18007af2d`
- `win32u!NtGdiPolyPatBlt` at `0x18007af2d`

## pseudocode

```c
__int64 __fastcall PolyPatBlt(HDC hdc, DWORD rop, HGDIOBJ *Src, unsigned int a4, int a5)
{
  __int64 v5; // r14
  unsigned int v9; // r13d
  unsigned int v10; // eax
  __int64 v11; // rdi
  unsigned __int16 v12; // bp
  struct _TEB *v13; // rbx
  HDC v14; // rax
  __int64 v15; // r12
  ULONG Offset; // eax
  int v17; // ecx
  HGDIOBJ v18; // rbp
  __int64 v19; // rbx
  __int64 v20; // rdi
  __int128 v22; // [rsp+30h] [rbp-68h] BYREF
  __int64 v23; // [rsp+40h] [rbp-58h]

  v5 = a4;
  v9 = 0;
  v10 = HANDLE_TO_INDEX(hdc);
  v11 = 0;
  if ( v10 < gMaxGdiHandleCount )
  {
    v22 = 0;
    v23 = 0;
    if ( (int)GdiGetEntry(v10, &v22) >= 0
      && BYTE14(v22) == 1
      && WORD6(v22) == WORD1(hdc)
      && (DWORD2(v22) & 0xFFFFFFFE) == gW32PID
      && v23 )
    {
      v11 = gCookie ^ __ROR8__(v23, 64 - (gCookie & 0x3Fu));
    }
  }
  if ( ((unsigned int)hdc & 0x7F0000) != 0x10000 || v11 && (*(_BYTE *)(v11 + 240) & 3) != 0 )
  {
    v18 = 0;
    v19 = 0;
    if ( (_DWORD)v5 )
    {
      do
      {
        if ( (_DWORD)v19 )
        {
          v20 = (unsigned int)v19;
          SelectObject(hdc, Src[3 * v19 + 2]);
        }
        else
        {
          v18 = SelectObject(hdc, Src[2]);
          v20 = 0;
        }
        v19 = (unsigned int)(v19 + 1);
        v9 = PatBlt(
               hdc,
               (int)Src[3 * v20],
               HIDWORD(Src[3 * v20]),
               (int)Src[3 * v20 + 1],
               HIDWORD(Src[3 * v20 + 1]),
               rop);
      }
      while ( (unsigned int)v19 < (unsigned int)v5 );
      if ( v18 )
        SelectObject(hdc, v18);
    }
  }
  else
  {
    LODWORD(NtCurrentTeb()->Win32ClientInfo[1]) = 0;
    if ( (_DWORD)v5 && Src && !a5 )
    {
      if ( (unsigned int)v5 > 0xAAA )
        return (unsigned int)NtGdiPolyPatBlt(hdc, rop, Src, (unsigned int)v5, 0);
      v12 = 24 * v5 + 56;
      if ( (unsigned __int16)(24 * v5) >= 0xFFC8u )
        return (unsigned int)NtGdiPolyPatBlt(hdc, rop, Src, (unsigned int)v5, 0);
      if ( (unsigned int)IsThreadDesktopComposited() )
        return (unsigned int)NtGdiPolyPatBlt(hdc, rop, Src, (unsigned int)v5, 0);
      v13 = NtCurrentTeb();
      v14 = (HDC)v13->GdiTebBatch.HDC;
      if ( v14 )
      {
        if ( v14 != hdc )
          return (unsigned int)NtGdiPolyPatBlt(hdc, rop, Src, (unsigned int)v5, 0);
      }
      if ( v12 > 0x4D8u )
        return (unsigned int)NtGdiPolyPatBlt(hdc, rop, Src, (unsigned int)v5, 0);
      if ( v12 + (v13->GdiTebBatch.Offset & 0x3FFFFFFF) > 0x4D8 )
        return (unsigned int)NtGdiPolyPatBlt(hdc, rop, Src, (unsigned int)v5, 0);
      if ( !v11 )
        return (unsigned int)NtGdiPolyPatBlt(hdc, rop, Src, (unsigned int)v5, 0);
      v9 = 1;
      if ( (*(_BYTE *)v11 & 1) != 0 )
      {
        return (unsigned int)NtGdiPolyPatBlt(hdc, rop, Src, (unsigned int)v5, 0);
      }
      else
      {
        if ( (v13->GdiTebBatch.Offset & 0x40000000) != 0 )
          TraceLoggingGdiBatchInProcessing(1);
        v15 = v13->GdiTebBatch.Offset & 0x3FFFFFFF;
        *(_WORD *)((char *)v13->GdiTebBatch.Buffer + v15 + 2) = 1;
        *(_WORD *)((char *)v13->GdiTebBatch.Buffer + v15) = (24 * v5 + 63) & 0xFFF8;
        *(_DWORD *)(v11 + 152) |= 0x200000u;
        *(ULONG *)((char *)&v13->GdiTebBatch.Buffer[1] + v15) = rop;
        *(ULONG *)((char *)&v13->GdiTebBatch.Buffer[3] + v15) = v5;
        *(ULONG *)((char *)&v13->GdiTebBatch.Buffer[2] + v15) = 0;
        *(ULONG *)((char *)&v13->GdiTebBatch.Buffer[4] + v15) = *(_DWORD *)(v11 + 184);
        *(ULONG *)((char *)&v13->GdiTebBatch.Buffer[5] + v15) = *(_DWORD *)(v11 + 176);
        *(ULONG *)((char *)&v13->GdiTebBatch.Buffer[6] + v15) = *(_DWORD *)(v11 + 192);
        *(_QWORD *)((char *)&v13->GdiTebBatch.Buffer[10] + v15) = *(_QWORD *)(v11 + 324);
        *(ULONG *)((char *)&v13->GdiTebBatch.Buffer[7] + v15) = *(_DWORD *)(v11 + 188);
        *(ULONG *)((char *)&v13->GdiTebBatch.Buffer[8] + v15) = *(_DWORD *)(v11 + 180);
        *(ULONG *)((char *)&v13->GdiTebBatch.Buffer[9] + v15) = *(_DWORD *)(v11 + 196);
        memcpy_0((char *)&v13->GdiTebBatch.Buffer[12] + v15, Src, 24 * v5);
        if ( !*(_QWORD *)((char *)&v13->GdiTebBatch.Buffer[16] + v15) )
          *(_QWORD *)((char *)&v13->GdiTebBatch.Buffer[16] + v15) = *(_QWORD *)(v11 + 160);
        if ( hdc )
        {
          v13->GdiTebBatch.HDC = hdc;
          if ( !*(_WORD *)((char *)v13->GdiTebBatch.Buffer + v15 + 2)
            || *(_WORD *)((char *)v13->GdiTebBatch.Buffer + v15 + 2) == 1
            || (unsigned int)*(unsigned __int16 *)((char *)v13->GdiTebBatch.Buffer + v15 + 2) - 2 <= 1 )
          {
            v13->GdiTebBatch.Offset |= 0x80000000;
          }
        }
        Offset = v13->GdiTebBatch.Offset;
        v17 = *(unsigned __int16 *)((char *)v13->GdiTebBatch.Buffer + v15);
        ++v13->GdiBatchCount;
        v13->GdiTebBatch.Offset = Offset ^ (Offset ^ (Offset + ((v17 + 7) & 0xFFFFFFF8))) & 0x3FFFFFFF;
        if ( v13->GdiBatchCount >= GdiBatchLimit )
          NtGdiFlush();
      }
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18007abf0  mov     [rsp+arg_8], edx
0x18007abf4  push    rbx
0x18007abf5  push    rbp
0x18007abf6  push    rsi
0x18007abf7  push    rdi
0x18007abf8  push    r12
0x18007abfa  push    r13
0x18007abfc  push    r14
0x18007abfe  push    r15
0x18007ac00  sub     rsp, 58h
0x18007ac04  mov     r14d, r9d
0x18007ac07  mov     r15, r8
0x18007ac0a  mov     r12d, edx
0x18007ac0d  mov     rsi, rcx
0x18007ac10  xor     r13d, r13d
0x18007ac13  call    HANDLE_TO_INDEX
0x18007ac18  mov     ecx, eax
0x18007ac1a  xor     edi, edi
0x18007ac1c  mov     rax, cs:__imp_gMaxGdiHandleCount
0x18007ac23  cmp     ecx, [rax]
0x18007ac25  jnb     short loc_18007ACA6
0x18007ac27  xorps   xmm0, xmm0
0x18007ac2a  lea     rdx, [rsp+98h+var_68]
0x18007ac2f  xor     eax, eax
0x18007ac31  movups  [rsp+98h+var_68], xmm0
0x18007ac36  mov     [rsp+98h+var_58], rax
0x18007ac3b  call    cs:__imp_GdiGetEntry
0x18007ac42  nop     dword ptr [rax+rax+00h]
0x18007ac47  test    eax, eax
0x18007ac49  js      short loc_18007ACA6
0x18007ac4b  cmp     byte ptr [rsp+98h+var_68+0Eh], 1
0x18007ac50  jnz     short loc_18007ACA6
0x18007ac52  movzx   eax, byte ptr [rsp+98h+var_68+0Ch]
0x18007ac57  movzx   ecx, byte ptr [rsp+98h+var_68+0Dh]
0x18007ac5c  shl     cx, 8
0x18007ac60  or      cx, ax
0x18007ac63  mov     eax, esi
0x18007ac65  shr     eax, 10h
0x18007ac68  cmp     cx, ax
0x18007ac6b  jnz     short loc_18007ACA6
0x18007ac6d  mov     rax, cs:__imp_gW32PID
0x18007ac74  mov     ecx, dword ptr [rsp+98h+var_68+8]
0x18007ac78  and     ecx, 0FFFFFFFEh
0x18007ac7b  cmp     ecx, [rax]
0x18007ac7d  jnz     short loc_18007ACA6
0x18007ac7f  mov     r8, [rsp+98h+var_58]
0x18007ac84  test    r8, r8
0x18007ac87  jz      short loc_18007ACA6
0x18007ac89  mov     rax, cs:__imp_gCookie
0x18007ac90  lea     ecx, [rdi+40h]
0x18007ac93  mov     rdi, r8
0x18007ac96  mov     rdx, [rax]
0x18007ac99  mov     eax, edx
0x18007ac9b  and     eax, 3Fh
0x18007ac9e  sub     ecx, eax
0x18007aca0  ror     rdi, cl
0x18007aca3  xor     rdi, rdx
0x18007aca6  mov     eax, esi
0x18007aca8  and     eax, 7F0000h
0x18007acad  cmp     eax, 10000h
0x18007acb2  jnz     loc_18007AF41
0x18007acb8  test    rdi, rdi
0x18007acbb  jz      short loc_18007ACCA
0x18007acbd  test    byte ptr [rdi+0F0h], 3
0x18007acc4  jnz     loc_18007AF41
0x18007acca  mov     rax, gs:30h
0x18007acd3  mov     [rax+808h], r13d
0x18007acda  test    r14d, r14d
0x18007acdd  jz      loc_18007AFC8
0x18007ace3  test    r15, r15
0x18007ace6  jz      loc_18007AFC8
0x18007acec  cmp     [rsp+98h+arg_20], r13d
0x18007acf4  jnz     loc_18007AFC8
0x18007acfa  cmp     r14d, 0AAAh
0x18007ad01  ja      loc_18007AF19
0x18007ad07  movzx   eax, r14w
0x18007ad0b  add     ax, ax
0x18007ad0e  lea     ebp, [rax+r14]
0x18007ad12  shl     bp, 3
0x18007ad16  add     bp, 38h ; '8'
0x18007ad1a  cmp     bp, 38h ; '8'
0x18007ad1e  jb      loc_18007AF19
0x18007ad24  call    cs:__imp_IsThreadDesktopComposited
0x18007ad2b  nop     dword ptr [rax+rax+00h]
0x18007ad30  test    eax, eax
0x18007ad32  jnz     loc_18007AF19
0x18007ad38  mov     rbx, gs:30h
0x18007ad41  mov     rax, [rbx+2F8h]
0x18007ad48  test    rax, rax
0x18007ad4b  jz      short loc_18007AD56
0x18007ad4d  cmp     rax, rsi
0x18007ad50  jnz     loc_18007AF19
0x18007ad56  mov     r8d, 4D8h
0x18007ad5c  cmp     bp, r8w
0x18007ad60  ja      loc_18007AF19
0x18007ad66  mov     edx, [rbx+2F0h]
0x18007ad6c  mov     ecx, edx
0x18007ad6e  and     ecx, 3FFFFFFFh
0x18007ad74  movzx   eax, bp
0x18007ad77  add     ecx, eax
0x18007ad79  cmp     ecx, r8d
0x18007ad7c  ja      loc_18007AF19
0x18007ad82  test    rdi, rdi
0x18007ad85  jz      loc_18007AF19
0x18007ad8b  mov     r13d, 1
0x18007ad91  test    [rdi], r13b
0x18007ad94  jnz     loc_18007AF19
0x18007ad9a  bt      edx, 1Eh
0x18007ad9e  jnb     short loc_18007ADA8
0x18007ada0  mov     ecx, r13d
0x18007ada3  call    TraceLoggingGdiBatchInProcessing
0x18007ada8  mov     r12d, [rbx+2F0h]
0x18007adaf  lea     r8, [r14+r14*2]
0x18007adb3  and     r12d, 3FFFFFFFh
0x18007adba  shl     r8, 3; Size
0x18007adbe  mov     eax, 0FFF8h
0x18007adc3  lea     rcx, [rbx+330h]
0x18007adca  add     bp, 7
0x18007adce  add     rcx, r12; void *
0x18007add1  and     bp, ax
0x18007add4  mov     rdx, r15; Src
0x18007add7  mov     eax, [rsp+98h+arg_8]
0x18007adde  mov     [r12+rbx+302h], r13w
0x18007ade7  mov     [r12+rbx+300h], bp
0x18007adf0  bts     dword ptr [rdi+98h], 15h
0x18007adf8  mov     [r12+rbx+304h], eax
0x18007ae00  mov     [r12+rbx+30Ch], r14d
0x18007ae08  mov     dword ptr [r12+rbx+308h], 0
0x18007ae14  mov     eax, [rdi+0B8h]
0x18007ae1a  mov     [r12+rbx+310h], eax
0x18007ae22  mov     eax, [rdi+0B0h]
0x18007ae28  mov     [r12+rbx+314h], eax
0x18007ae30  mov     eax, [rdi+0C0h]
0x18007ae36  mov     [r12+rbx+318h], eax
0x18007ae3e  mov     rax, [rdi+144h]
0x18007ae45  mov     [r12+rbx+328h], rax
0x18007ae4d  mov     eax, [rdi+0BCh]
0x18007ae53  mov     [r12+rbx+31Ch], eax
0x18007ae5b  mov     eax, [rdi+0B4h]
0x18007ae61  mov     [r12+rbx+320h], eax
0x18007ae69  mov     eax, [rdi+0C4h]
0x18007ae6f  mov     [r12+rbx+324h], eax
0x18007ae77  call    memcpy_0
0x18007ae7c  cmp     qword ptr [r12+rbx+340h], 0
0x18007ae85  jnz     short loc_18007AE96
0x18007ae87  mov     rax, [rdi+0A0h]
0x18007ae8e  mov     [r12+rbx+340h], rax
0x18007ae96  test    rsi, rsi
0x18007ae99  jz      short loc_18007AEC6
0x18007ae9b  mov     [rbx+2F8h], rsi
0x18007aea2  movzx   ecx, word ptr [r12+rbx+302h]
0x18007aeab  test    ecx, ecx
0x18007aead  jz      short loc_18007AEBE
0x18007aeaf  sub     ecx, r13d
0x18007aeb2  jz      short loc_18007AEBE
0x18007aeb4  sub     ecx, r13d
0x18007aeb7  jz      short loc_18007AEBE
0x18007aeb9  cmp     ecx, r13d
0x18007aebc  jnz     short loc_18007AEC6
0x18007aebe  bts     dword ptr [rbx+2F0h], 1Fh
0x18007aec6  mov     eax, [rbx+2F0h]
0x18007aecc  movzx   ecx, word ptr [r12+rbx+300h]
0x18007aed5  inc     dword ptr [rbx+1740h]
0x18007aedb  add     ecx, 7
0x18007aede  and     ecx, 0FFFFFFF8h
0x18007aee1  add     ecx, eax
0x18007aee3  xor     ecx, eax
0x18007aee5  and     ecx, 3FFFFFFFh
0x18007aeeb  xor     ecx, eax
0x18007aeed  mov     rax, cs:__imp_GdiBatchLimit
0x18007aef4  mov     [rbx+2F0h], ecx
0x18007aefa  mov     ecx, [rbx+1740h]
0x18007af00  cmp     ecx, [rax]
0x18007af02  jb      loc_18007AFC8
0x18007af08  call    cs:__imp_NtGdiFlush
0x18007af0f  nop     dword ptr [rax+rax+00h]
0x18007af14  jmp     loc_18007AFC8
0x18007af19  mov     r9d, r14d
0x18007af1c  mov     [rsp+98h+h], 0
0x18007af24  mov     r8, r15
0x18007af27  mov     edx, r12d
0x18007af2a  mov     rcx, rsi
0x18007af2d  call    cs:__imp_NtGdiPolyPatBlt
0x18007af34  nop     dword ptr [rax+rax+00h]
0x18007af39  mov     r13d, eax
0x18007af3c  jmp     loc_18007AFC8
0x18007af41  xor     ebp, ebp
0x18007af43  xor     ebx, ebx
0x18007af45  test    r14d, r14d
0x18007af48  jz      short loc_18007AFC8
0x18007af4a  mov     rcx, rsi; hdc
0x18007af4d  test    ebx, ebx
0x18007af4f  jnz     short loc_18007AF68
0x18007af51  mov     rdx, [r15+10h]; h
0x18007af55  call    cs:__imp_SelectObject
0x18007af5c  nop     dword ptr [rax+rax+00h]
0x18007af61  mov     rbp, rax
0x18007af64  xor     edi, edi
0x18007af66  jmp     short loc_18007AF7F
0x18007af68  lea     rdx, [rbx+rbx*2]
0x18007af6c  mov     edi, ebx
0x18007af6e  mov     rdx, [r15+rdx*8+10h]; h
0x18007af73  call    cs:__imp_SelectObject
0x18007af7a  nop     dword ptr [rax+rax+00h]
0x18007af7f  lea     rdx, [rdi+rdi*2]
0x18007af83  mov     [rsp+98h+rop], r12d; rop
0x18007af88  mov     eax, [r15+rdx*8+0Ch]
0x18007af8d  mov     rcx, rsi; hdc
0x18007af90  mov     r9d, [r15+rdx*8+8]; w
0x18007af95  mov     r8d, [r15+rdx*8+4]; y
0x18007af9a  mov     edx, [r15+rdx*8]; x
0x18007af9e  mov     [rsp+98h+h], eax; h
0x18007afa2  call    PatBlt
0x18007afa7  inc     ebx
0x18007afa9  mov     r13d, eax
0x18007afac  cmp     ebx, r14d
0x18007afaf  jb      short loc_18007AF4A
0x18007afb1  test    rbp, rbp
0x18007afb4  jz      short loc_18007AFC8
0x18007afb6  mov     rdx, rbp; h
0x18007afb9  mov     rcx, rsi; hdc
0x18007afbc  call    cs:__imp_SelectObject
0x18007afc3  nop     dword ptr [rax+rax+00h]
0x18007afc8  mov     eax, r13d
0x18007afcb  add     rsp, 58h
0x18007afcf  pop     r15
0x18007afd1  pop     r14
0x18007afd3  pop     r13
0x18007afd5  pop     r12
0x18007afd7  pop     rdi
0x18007afd8  pop     rsi
0x18007afd9  pop     rbp
0x18007afda  pop     rbx
0x18007afdb  retn
```
