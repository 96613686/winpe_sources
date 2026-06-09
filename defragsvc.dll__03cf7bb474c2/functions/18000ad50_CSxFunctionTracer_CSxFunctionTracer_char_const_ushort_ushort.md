# CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)

- ea: `0x18000ad50`
- end: `0x18000ae62`
- name: `??0CSxFunctionTracer@@QEAA@PEBDGG@Z`
- size: `274`
- prototype: `CSxFunctionTracer *__fastcall(CSxFunctionTracer *this, const char *, __int16, __int16)`
- caller_count: `524`
- callee_count: `3`
- tags: ``

## callers

- `0x180003b3c`
- `0x180003c30`
- `0x180003d84`
- `0x180008980`
- `0x180008c30`
- `0x180008df0`
- `0x180008ea0`
- `0x180009050`
- `0x1800091b0`
- `0x180009260`
- `0x180009440`
- `0x180009800`
- `0x180009a30`
- `0x180009c50`
- `0x180009d00`
- `0x180009f10`
- `0x18000a410`
- `0x18000a530`
- `0x18000a9a0`
- `0x18000ab40`
- `0x18000ae70`
- `0x18000c644`
- `0x18000c794`
- `0x18000c848`
- `0x18000c990`
- `0x18000cae8`
- `0x18000d740`
- `0x18000e110`
- `0x18000e168`
- `0x18000e218`
- `0x18000e4e0`
- `0x18000f328`
- `0x18000fcac`
- `0x18000fe24`
- `0x18000ff80`
- `0x180010c20`
- `0x18001113c`
- `0x1800114cc`
- `0x1800118d8`
- `0x1800119c8`
- `0x180011b04`
- `0x180011d10`
- `0x180011f48`
- `0x1800121fc`
- `0x180012474`
- `0x1800125e4`
- `0x1800126b0`
- `0x1800128b8`
- `0x180012a48`
- `0x180012aa4`

## callees

- `0x18000ad50`
- `0x180046494`
- `0x18004a92c`

## import_xrefs

- `SXSHARED!SxTracerGetThreadContextRetail` at `0x18000ad8e`
- `SXSHARED!SxTracerGetThreadContextRetail` at `0x18000ad8e`

## pseudocode

```c
CSxFunctionTracer *__fastcall CSxFunctionTracer::CSxFunctionTracer(
        CSxFunctionTracer *this,
        const char *a2,
        __int16 a3,
        __int16 a4)
{
  int ThreadContextRetail; // eax
  __int64 v6; // rcx
  CSxGlobalTracer *v7; // rcx
  __int16 v8; // ax
  __int64 v10; // rdx

  *(_DWORD *)this = 0;
  *((_WORD *)this + 3) = 0;
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_WORD *)this + 2) = a3;
  *((_WORD *)this + 6) = a4;
  *((_QWORD *)this + 2) = a2;
  ThreadContextRetail = SxTracerGetThreadContextRetail((char *)this + 32);
  if ( ThreadContextRetail >= 0 )
  {
    v6 = *((_QWORD *)this + 4);
    *((_QWORD *)this + 3) = *(_QWORD *)(v6 + 32);
    *(_QWORD *)(v6 + 32) = this;
LABEL_3:
    v7 = WPP_GLOBAL_Control;
    goto LABEL_4;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids,
      (unsigned int)ThreadContextRetail);
    goto LABEL_3;
  }
LABEL_4:
  v8 = *((_WORD *)this + 6);
  if ( v8 )
  {
    if ( v8 == 1 )
    {
      if ( v7 == (CSxGlobalTracer *)&WPP_GLOBAL_Control || (*((_DWORD *)v7 + 7) & 0x20000000) == 0 )
        return this;
      v10 = 12;
LABEL_12:
      WPP_SF_s(*((_QWORD *)v7 + 2), v10, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids, *((_QWORD *)this + 2));
      return this;
    }
    if ( v7 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x20000) != 0 )
    {
      v10 = 13;
      goto LABEL_12;
    }
  }
  else if ( v7 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x8000000) != 0 )
  {
    v10 = 11;
    goto LABEL_12;
  }
  return this;
}

```

## disassembly

```asm
0x18000ad50  mov     [rsp+arg_0], rbx
0x18000ad55  mov     [rsp+arg_8], rsi
0x18000ad5a  push    rdi
0x18000ad5b  sub     rsp, 20h
0x18000ad5f  mov     rbx, rcx
0x18000ad62  xor     ecx, ecx
0x18000ad64  mov     [rbx], ecx
0x18000ad66  mov     [rbx+6], cx
0x18000ad6a  mov     [rbx+8], ecx
0x18000ad6d  mov     [rbx+18h], rcx
0x18000ad71  mov     [rbx+20h], rcx
0x18000ad75  mov     [rbx+28h], rcx
0x18000ad79  mov     [rbx+30h], ecx
0x18000ad7c  lea     rcx, [rbx+20h]
0x18000ad80  mov     [rbx+4], r8w
0x18000ad85  mov     [rbx+0Ch], r9w
0x18000ad8a  mov     [rbx+10h], rdx
0x18000ad8e  call    cs:__imp_SxTracerGetThreadContextRetail
0x18000ad94  lea     rsi, WPP_GLOBAL_Control
0x18000ad9b  test    eax, eax
0x18000ad9d  js      short loc_18000AE17
0x18000ad9f  mov     rcx, [rbx+20h]
0x18000ada3  mov     rax, [rcx+20h]
0x18000ada7  mov     [rbx+18h], rax
0x18000adab  mov     [rcx+20h], rbx
0x18000adaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000adb6  movzx   eax, word ptr [rbx+0Ch]
0x18000adba  test    ax, ax
0x18000adbd  jz      loc_18000AE46
0x18000adc3  cmp     ax, 1
0x18000adc7  jnz     short loc_18000ADEE
0x18000adc9  cmp     rcx, rsi
0x18000adcc  jz      short loc_18000ADDB
0x18000adce  test    dword ptr [rcx+1Ch], 20000000h
0x18000add5  jnz     loc_18000AE5B
0x18000addb  mov     rsi, [rsp+28h+arg_8]
0x18000ade0  mov     rax, rbx
0x18000ade3  mov     rbx, [rsp+28h+arg_0]
0x18000ade8  add     rsp, 20h
0x18000adec  pop     rdi
0x18000aded  retn
0x18000adee  cmp     rcx, rsi
0x18000adf1  jz      short loc_18000ADDB
0x18000adf3  test    dword ptr [rcx+1Ch], 20000h
0x18000adfa  jz      short loc_18000ADDB
0x18000adfc  mov     edx, 0Dh
0x18000ae01  mov     r9, [rbx+10h]
0x18000ae05  lea     r8, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids
0x18000ae0c  mov     rcx, [rcx+10h]
0x18000ae10  call    WPP_SF_s
0x18000ae15  jmp     short loc_18000ADDB
0x18000ae17  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae1e  cmp     rcx, rsi
0x18000ae21  jz      short loc_18000ADB6
0x18000ae23  test    byte ptr [rcx+1Ch], 1
0x18000ae27  jz      short loc_18000ADB6
0x18000ae29  mov     rcx, [rcx+10h]
0x18000ae2d  lea     r8, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids
0x18000ae34  mov     edx, 0Ah
0x18000ae39  mov     r9d, eax
0x18000ae3c  call    WPP_SF_d
0x18000ae41  jmp     loc_18000ADAF
0x18000ae46  cmp     rcx, rsi
0x18000ae49  jz      short loc_18000ADDB
0x18000ae4b  test    dword ptr [rcx+1Ch], 8000000h
0x18000ae52  jz      short loc_18000ADDB
0x18000ae54  mov     edx, 0Bh
0x18000ae59  jmp     short loc_18000AE01
0x18000ae5b  mov     edx, 0Ch
0x18000ae60  jmp     short loc_18000AE01
```
