# SQLConfigDataSourceCover

- ea: `0x1800084c0`
- end: `0x180008564`
- name: `SQLConfigDataSourceCover`
- size: `164`
- prototype: `BOOL __fastcall(HWND, unsigned __int16, const wchar_t *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180008570`

## callees

- `0x180001740`
- `0x180004bac`
- `0x180007c0c`
- `0x1800084c0`
- `0x1800099a0`

## pseudocode

```c
BOOL __fastcall SQLConfigDataSourceCover(HWND a1, unsigned __int16 a2, const wchar_t *a3, __int64 a4)
{
  __int16 v6; // bx
  unsigned __int16 v7; // dx
  int v8; // eax
  int v9; // edi
  int v10; // ecx

  if ( a2 == 7 )
    return SQLRemoveDefaultDataSource();
  if ( (unsigned __int16)(a2 - 1) > 5u )
  {
    v10 = 5;
    goto LABEL_13;
  }
  if ( !a3 || !*a3 )
  {
    v10 = 7;
LABEL_13:
    PostInstError(v10);
    return 0;
  }
  v6 = g_wSystemDSN;
  v7 = a2 - 3;
  g_wSystemDSN = (a2 < 4u) + 1;
  if ( a2 < 4u )
    v7 = a2;
  v8 = ConfigDataSourceW(a1, v7, a3, a4);
  g_wSystemDSN = v6;
  v9 = v8;
  if ( v8 )
    FreeErrorQueue();
  return v9;
}

```

## disassembly

```asm
0x1800084c0  mov     [rsp+arg_0], rbx
0x1800084c5  mov     [rsp+arg_8], rsi
0x1800084ca  push    rdi
0x1800084cb  sub     rsp, 20h
0x1800084cf  mov     r11d, 7
0x1800084d5  movzx   r10d, dx
0x1800084d9  cmp     dx, r11w
0x1800084dd  jnz     short loc_1800084E6
0x1800084df  call    SQLRemoveDefaultDataSource
0x1800084e4  jmp     short loc_180008554
0x1800084e6  lea     eax, [r10-1]
0x1800084ea  mov     edx, 5
0x1800084ef  cmp     ax, dx
0x1800084f2  ja      short loc_18000854B
0x1800084f4  xor     esi, esi
0x1800084f6  test    r8, r8
0x1800084f9  jz      short loc_180008546
0x1800084fb  cmp     [r8], si
0x1800084ff  jz      short loc_180008546
0x180008501  movzx   ebx, cs:g_wSystemDSN
0x180008508  lea     edx, [r10-3]
0x18000850c  cmp     r10w, 4
0x180008511  sbb     ax, ax
0x180008514  neg     ax
0x180008517  inc     ax
0x18000851a  cmp     r10w, 4
0x18000851f  mov     cs:g_wSystemDSN, ax
0x180008526  cmovb   dx, r10w
0x18000852b  call    ConfigDataSourceW
0x180008530  mov     cs:g_wSystemDSN, bx
0x180008537  mov     edi, eax
0x180008539  test    eax, eax
0x18000853b  jz      short loc_180008542
0x18000853d  call    FreeErrorQueue
0x180008542  mov     eax, edi
0x180008544  jmp     short loc_180008554
0x180008546  mov     ecx, r11d
0x180008549  jmp     short loc_18000854D
0x18000854b  mov     ecx, edx
0x18000854d  call    PostInstError
0x180008552  xor     eax, eax
0x180008554  mov     rbx, [rsp+28h+arg_0]
0x180008559  mov     rsi, [rsp+28h+arg_8]
0x18000855e  add     rsp, 20h
0x180008562  pop     rdi
0x180008563  retn
```
