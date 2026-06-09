# HbpTraceEvent

- ea: `0x140001600`
- end: `0x140001782`
- name: `HbpTraceEvent`
- size: `386`
- prototype: `char(int, const CHAR *, int, const char *, ...)`
- caller_count: `35`
- callee_count: `6`
- tags: ``

## callers

- `0x140001340`
- `0x1400013c0`
- `0x140001460`
- `0x1400017c0`
- `0x140001900`
- `0x140001b50`
- `0x140001bfc`
- `0x140001e20`
- `0x140001f6c`
- `0x14000e260`
- `0x14000e520`
- `0x14000ebb0`
- `0x14000ec10`
- `0x14000ec70`
- `0x14000ecd0`
- `0x14000f948`
- `0x14000fc48`
- `0x1400104f0`
- `0x1400105d4`
- `0x140010700`
- `0x140010914`
- `0x140010a78`
- `0x140010c0c`
- `0x140011420`
- `0x140011760`
- `0x140011e18`
- `0x140012080`
- `0x140012170`
- `0x14001274c`
- `0x140012abc`
- `0x1400137b0`
- `0x1400140f0`
- `0x1400146d0`
- `0x140014810`
- `0x140015078`

## callees

- `0x140001008`
- `0x140001040`
- `0x140001070`
- `0x140001600`
- `0x140002ae0`
- `0x140002f00`

## import_xrefs

- `ntoskrnl!_vsnprintf` at `0x14000166a`
- `ntoskrnl!_vsnprintf` at `0x14000166a`

## pseudocode

```c
char HbpTraceEvent(int a1, const CHAR *a2, int a3, const char *a4, ...)
{
  unsigned int v8; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rax
  int v13; // [rsp+30h] [rbp-D0h] BYREF
  int v14; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v15; // [rsp+38h] [rbp-C8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+40h] [rbp-C0h] BYREF
  int *v17; // [rsp+60h] [rbp-A0h]
  __int64 v18; // [rsp+68h] [rbp-98h]
  _BYTE v19[16]; // [rsp+70h] [rbp-90h] BYREF
  int *v20; // [rsp+80h] [rbp-80h]
  __int64 v21; // [rsp+88h] [rbp-78h]
  char *v22; // [rsp+90h] [rbp-70h]
  int v23; // [rsp+98h] [rbp-68h]
  int v24; // [rsp+9Ch] [rbp-64h]
  __int64 *v25; // [rsp+A0h] [rbp-60h]
  __int64 v26; // [rsp+A8h] [rbp-58h]
  char Dest[512]; // [rsp+B0h] [rbp-50h] BYREF
  va_list Args; // [rsp+320h] [rbp+220h] BYREF

  va_start(Args, a4);
  v15 = 0;
  memset(Dest, 0, sizeof(Dest));
  v8 = _vsnprintf(Dest, 0x1FFu, a4, Args);
  if ( v8 < 0x200 )
  {
    if ( v8 == 511 )
      Dest[511] = 0;
    LOBYTE(v8) = dword_140009088;
    if ( (unsigned int)dword_140009088 > 5 )
    {
      LOBYTE(v8) = tlgKeywordOn((__int64)&dword_140009088, 0x400000000000LL);
      if ( (_BYTE)v8 )
      {
        v13 = a1;
        v17 = &v13;
        v18 = 4;
        tlgCreate1Sz_char((__int64)v19, a2);
        v14 = a3;
        v20 = &v14;
        v11 = -1;
        v21 = 4;
        do
          ++v11;
        while ( Dest[v11] );
        v24 = 0;
        v23 = v11 + 1;
        v22 = Dest;
        v25 = &v15;
        v15 = 0x2000000;
        v26 = 8;
        LOBYTE(v8) = tlgWriteTransfer_EtwWriteTransfer(
                       (__int64)&dword_140009088,
                       (unsigned __int8 *)&byte_140007241,
                       v9,
                       v10,
                       7u,
                       &v16);
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x140001600  mov     [rsp-8+arg_18], r9
0x140001605  push    rbp
0x140001606  push    rbx
0x140001607  push    rsi
0x140001608  push    rdi
0x140001609  push    r14
0x14000160b  push    r15
0x14000160d  lea     rbp, [rsp-1C8h]
0x140001615  sub     rsp, 2C8h
0x14000161c  mov     rax, cs:__security_cookie
0x140001623  xor     rax, rsp
0x140001626  mov     [rbp+1F0h+var_40], rax
0x14000162d  mov     edi, r8d
0x140001630  mov     [rsp+2F0h+var_2B8], 0
0x140001639  mov     r14, rdx
0x14000163c  lea     r15, [rbp+1F0h+Args]
0x140001643  mov     esi, ecx
0x140001645  xor     edx, edx; Val
0x140001647  mov     r8d, 200h; Size
0x14000164d  lea     rcx, [rbp+1F0h+Dest]; void *
0x140001651  mov     rbx, r9
0x140001654  call    memset
0x140001659  mov     r8, rbx; Format
0x14000165c  lea     rcx, [rbp+1F0h+Dest]; Dest
0x140001660  mov     ebx, 1FFh
0x140001665  mov     r9, r15; Args
0x140001668  mov     edx, ebx; Count
0x14000166a  call    cs:__imp__vsnprintf
0x140001671  nop     dword ptr [rax+rax+00h]
0x140001676  test    eax, eax
0x140001678  js      loc_14000175B
0x14000167e  cmp     eax, ebx
0x140001680  ja      loc_14000175B
0x140001686  jnz     short loc_14000168F
0x140001688  mov     [rbp+1F0h+var_41], 0
0x14000168f  mov     eax, cs:dword_140009088
0x140001695  cmp     eax, 5
0x140001698  jbe     loc_140001762
0x14000169e  mov     rdx, 400000000000h
0x1400016a8  lea     rcx, dword_140009088
0x1400016af  call    _tlgKeywordOn
0x1400016b4  test    al, al
0x1400016b6  jz      loc_140001762
0x1400016bc  lea     rax, [rsp+2F0h+var_2C0]
0x1400016c1  mov     [rsp+2F0h+var_2C0], esi
0x1400016c5  mov     rdx, r14
0x1400016c8  mov     [rsp+2F0h+var_290], rax
0x1400016cd  lea     rcx, [rsp+2F0h+var_280]
0x1400016d2  mov     [rsp+2F0h+var_288], 4
0x1400016db  call    _tlgCreate1Sz_char
0x1400016e0  lea     rax, [rsp+2F0h+var_2BC]
0x1400016e5  mov     [rsp+2F0h+var_2BC], edi
0x1400016e9  mov     [rbp+1F0h+var_270], rax
0x1400016ed  lea     rcx, [rbp+1F0h+Dest]
0x1400016f1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400016f5  mov     [rbp+1F0h+var_268], 4
0x1400016fd  inc     rax
0x140001700  cmp     byte ptr [rcx+rax], 0
0x140001704  jnz     short loc_1400016FD
0x140001706  inc     eax
0x140001708  mov     [rbp+1F0h+var_254], 0
0x14000170f  mov     [rbp+1F0h+var_258], eax
0x140001712  lea     rdx, [rbp+1F0h+Dest]
0x140001716  lea     rax, [rsp+2F0h+var_2B8]
0x14000171b  mov     [rbp+1F0h+var_260], rdx
0x14000171f  mov     [rbp+1F0h+var_250], rax
0x140001723  lea     rdx, byte_140007241; int
0x14000172a  lea     rax, [rsp+2F0h+var_2B0]
0x14000172f  mov     [rsp+2F0h+var_2B8], 2000000h
0x140001738  mov     [rsp+2F0h+var_2C8], rax; __int64
0x14000173d  lea     rcx, dword_140009088; int
0x140001744  mov     [rsp+2F0h+var_2D0], 7; ULONG
0x14000174c  mov     [rbp+1F0h+var_248], 8
0x140001754  call    _tlgWriteTransfer_EtwWriteTransfer
0x140001759  jmp     short loc_140001762
0x14000175b  mov     [rbp+1F0h+var_41], 0
0x140001762  mov     rcx, [rbp+1F0h+var_40]
0x140001769  xor     rcx, rsp; StackCookie
0x14000176c  call    __security_check_cookie
0x140001771  add     rsp, 2C8h
0x140001778  pop     r15
0x14000177a  pop     r14
0x14000177c  pop     rdi
0x14000177d  pop     rsi
0x14000177e  pop     rbx
0x14000177f  pop     rbp
0x140001780  retn
```
