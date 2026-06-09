# I8xGetControllerCommand

- ea: `0x140005830`
- end: `0x1400059b8`
- name: `I8xGetControllerCommand`
- size: `392`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140005560`

## callees

- `0x140004530`
- `0x140005830`
- `0x1400059c0`
- `0x1400066d0`

## import_xrefs

- `HAL!KeStallExecutionProcessor` at `0x140005923`
- `HAL!KeStallExecutionProcessor` at `0x140005923`

## pseudocode

```c
__int64 __fastcall I8xGetControllerCommand(__int64 a1, _BYTE *a2, __int64 a3, __int64 a4)
{
  char v5; // di
  int v6; // ebx
  __int64 result; // rax
  int v8; // edi
  int BytePolled; // ebp
  int v10; // edx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  unsigned int i; // r14d
  int v15; // eax
  int v16; // eax

  v5 = a1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      19,
      28,
      (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
  v6 = v5 & 1;
  if ( (v5 & 1) == 0
    || (LOBYTE(a4) = -83, LOBYTE(a3) = 3, LOBYTE(a1) = 1, result = I8xPutBytePolled(a1, 0, a3, a4), (int)result >= 0) )
  {
    v8 = v5 & 2;
    if ( v8
      && (LOBYTE(a4) = -89, LOBYTE(a3) = 3, LOBYTE(a1) = 1, BytePolled = I8xPutBytePolled(a1, 0, a3, a4), BytePolled < 0) )
    {
      if ( v6 )
      {
        LOBYTE(a4) = -82;
        LOBYTE(a3) = 3;
        LOBYTE(a1) = 1;
        I8xPutBytePolled(a1, 0, a3, a4);
      }
    }
    else
    {
      LOBYTE(a4) = 32;
      LOBYTE(a3) = 3;
      LOBYTE(a1) = 1;
      BytePolled = I8xPutBytePolled(a1, 0, a3, a4);
      if ( BytePolled >= 0 )
      {
        for ( i = 0; i < 5; ++i )
        {
          BytePolled = I8xGetBytePolled(0, a2);
          if ( BytePolled != -1073741643 )
            break;
          KeStallExecutionProcessor(0x32u);
        }
      }
      if ( v6 )
      {
        LOBYTE(v13) = -82;
        LOBYTE(v12) = 3;
        LOBYTE(v11) = 1;
        v15 = I8xPutBytePolled(v11, 0, v12, v13);
        if ( v15 >= 0 )
        {
          if ( !BytePolled )
            *a2 &= ~0x10u;
        }
        else if ( BytePolled >= 0 )
        {
          BytePolled = v15;
        }
      }
      if ( v8 )
      {
        LOBYTE(v13) = -88;
        LOBYTE(v12) = 3;
        LOBYTE(v11) = 1;
        v16 = I8xPutBytePolled(v11, 0, v12, v13);
        if ( BytePolled >= 0 )
        {
          if ( v16 >= 0 )
            *a2 &= ~0x20u;
          else
            BytePolled = v16;
        }
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          19,
          29,
          (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
    }
    return (unsigned int)BytePolled;
  }
  return result;
}

```

## disassembly

```asm
0x140005830  mov     [rsp+arg_10], rbx
0x140005835  mov     [rsp+arg_18], rsi
0x14000583a  push    rdi
0x14000583b  push    r12
0x14000583d  push    r15
0x14000583f  sub     rsp, 30h
0x140005843  mov     rsi, rdx
0x140005846  mov     edi, ecx
0x140005848  lea     r15, WPP_RECORDER_INITIALIZED
0x14000584f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140005856  lea     r12, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x14000585d  jnz     short loc_14000588E
0x14000585f  mov     ebx, edi
0x140005861  and     ebx, 1
0x140005864  jz      short loc_1400058B1
0x140005866  mov     r9b, 0ADh
0x140005869  mov     r8b, 3
0x14000586c  xor     edx, edx
0x14000586e  mov     cl, 1
0x140005870  call    I8xPutBytePolled
0x140005875  test    eax, eax
0x140005877  jns     short loc_1400058B1
0x140005879  mov     rbx, [rsp+48h+arg_10]
0x14000587e  mov     rsi, [rsp+48h+arg_18]
0x140005883  add     rsp, 30h
0x140005887  pop     r15
0x140005889  pop     r12
0x14000588b  pop     rdi
0x14000588c  retn
0x14000588e  mov     rcx, cs:WPP_GLOBAL_Control
0x140005895  mov     r9d, 1Ch
0x14000589b  mov     r8d, 13h
0x1400058a1  mov     [rsp+48h+var_28], r12
0x1400058a6  mov     rcx, [rcx+40h]
0x1400058aa  call    WPP_RECORDER_SF_
0x1400058af  jmp     short loc_14000585F
0x1400058b1  mov     [rsp+48h+arg_0], rbp
0x1400058b6  and     edi, 2
0x1400058b9  jz      short loc_1400058EE
0x1400058bb  mov     r9b, 0A7h
0x1400058be  mov     r8b, 3
0x1400058c1  xor     edx, edx
0x1400058c3  mov     cl, 1
0x1400058c5  call    I8xPutBytePolled
0x1400058ca  mov     ebp, eax
0x1400058cc  test    eax, eax
0x1400058ce  jns     short loc_1400058EE
0x1400058d0  test    ebx, ebx
0x1400058d2  jnz     short loc_1400058DD
0x1400058d4  mov     eax, ebp
0x1400058d6  mov     rbp, [rsp+48h+arg_0]
0x1400058db  jmp     short loc_140005879
0x1400058dd  mov     r9b, 0AEh
0x1400058e0  mov     r8b, 3
0x1400058e3  xor     edx, edx
0x1400058e5  mov     cl, 1
0x1400058e7  call    I8xPutBytePolled
0x1400058ec  jmp     short loc_1400058D4
0x1400058ee  mov     r9b, 20h ; ' '
0x1400058f1  mov     r8b, 3
0x1400058f4  xor     edx, edx
0x1400058f6  mov     cl, 1
0x1400058f8  call    I8xPutBytePolled
0x1400058fd  mov     ebp, eax
0x1400058ff  test    eax, eax
0x140005901  js      short loc_14000593D
0x140005903  mov     [rsp+48h+arg_8], r14
0x140005908  xor     r14d, r14d
0x14000590b  mov     rdx, rsi
0x14000590e  xor     ecx, ecx
0x140005910  call    I8xGetBytePolled
0x140005915  mov     ebp, eax
0x140005917  cmp     eax, 0C00000B5h
0x14000591c  jnz     short loc_140005938
0x14000591e  mov     ecx, 32h ; '2'; MicroSeconds
0x140005923  call    cs:__imp_KeStallExecutionProcessor
0x14000592a  nop     dword ptr [rax+rax+00h]
0x14000592f  inc     r14d
0x140005932  cmp     r14d, 5
0x140005936  jb      short loc_14000590B
0x140005938  mov     r14, [rsp+48h+arg_8]
0x14000593d  test    ebx, ebx
0x14000593f  jz      short loc_140005963
0x140005941  mov     r9b, 0AEh
0x140005944  mov     r8b, 3
0x140005947  xor     edx, edx
0x140005949  mov     cl, 1
0x14000594b  call    I8xPutBytePolled
0x140005950  test    eax, eax
0x140005952  jns     short loc_14000595C
0x140005954  test    ebp, ebp
0x140005956  js      short loc_140005963
0x140005958  mov     ebp, eax
0x14000595a  jmp     short loc_140005963
0x14000595c  test    ebp, ebp
0x14000595e  jnz     short loc_140005963
0x140005960  and     byte ptr [rsi], 0EFh
0x140005963  test    edi, edi
0x140005965  jz      short loc_140005985
0x140005967  mov     r9b, 0A8h
0x14000596a  mov     r8b, 3
0x14000596d  xor     edx, edx
0x14000596f  mov     cl, 1
0x140005971  call    I8xPutBytePolled
0x140005976  test    ebp, ebp
0x140005978  js      short loc_140005985
0x14000597a  test    eax, eax
0x14000597c  jns     short loc_140005982
0x14000597e  mov     ebp, eax
0x140005980  jmp     short loc_140005985
0x140005982  and     byte ptr [rsi], 0DFh
0x140005985  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000598c  jz      loc_1400058D4
0x140005992  mov     rcx, cs:WPP_GLOBAL_Control
0x140005999  mov     r9d, 1Dh
0x14000599f  mov     r8d, 13h
0x1400059a5  mov     [rsp+48h+var_28], r12
0x1400059aa  mov     rcx, [rcx+40h]
0x1400059ae  call    WPP_RECORDER_SF_
0x1400059b3  jmp     loc_1400058D4
```
