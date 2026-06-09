# NFSFreeLanList

- ea: `0x14000429c`
- end: `0x14000436c`
- name: `NFSFreeLanList`
- size: `208`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000664c`

## callees

- `0x140002bd8`
- `0x14000429c`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x1400042da`
- `KERNEL32!GlobalFree` at `0x140004308`
- `KERNEL32!GlobalFree` at `0x140004323`
- `KERNEL32!GlobalFree` at `0x1400042da`
- `KERNEL32!GlobalFree` at `0x140004308`
- `KERNEL32!GlobalFree` at `0x140004323`
- `KERNEL32!DeleteCriticalSection` at `0x14000431a`
- `KERNEL32!DeleteCriticalSection` at `0x14000431a`

## pseudocode

```c
HGLOBAL NFSFreeLanList()
{
  HGLOBAL result; // rax
  char *v1; // rdi
  _QWORD *v2; // rcx
  char *v3; // rsi
  _QWORD *v4; // rbx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_90b53e51910230494b81f4a05de1546d_Traceguids);
  result = GlobalFree(hObjects);
  v1 = (char *)pLanHead;
  hObjects = 0;
  if ( pLanHead )
  {
    do
    {
      v2 = (_QWORD *)*((_QWORD *)v1 + 4);
      v3 = (char *)*((_QWORD *)v1 + 6);
      if ( v2 )
      {
        do
        {
          v4 = (_QWORD *)v2[2];
          GlobalFree(v2);
          v2 = v4;
        }
        while ( v4 );
      }
      DeleteCriticalSection((LPCRITICAL_SECTION)(v1 + 64));
      result = GlobalFree(v1);
      v1 = v3;
    }
    while ( v3 );
  }
  pLanHead = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    return (HGLOBAL)WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_90b53e51910230494b81f4a05de1546d_Traceguids);
  return result;
}

```

## disassembly

```asm
0x14000429c  push    rbx
0x14000429e  push    rbp
0x14000429f  push    rsi
0x1400042a0  push    rdi
0x1400042a1  sub     rsp, 28h
0x1400042a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400042ac  lea     rbp, WPP_GLOBAL_Control
0x1400042b3  cmp     rcx, rbp
0x1400042b6  jz      short loc_1400042D3
0x1400042b8  test    byte ptr [rcx+1Ch], 1
0x1400042bc  jz      short loc_1400042D3
0x1400042be  mov     rcx, [rcx+10h]
0x1400042c2  lea     r8, WPP_90b53e51910230494b81f4a05de1546d_Traceguids
0x1400042c9  mov     edx, 47h ; 'G'
0x1400042ce  call    WPP_SF_
0x1400042d3  mov     rcx, cs:hObjects; hMem
0x1400042da  call    cs:__imp_GlobalFree
0x1400042e0  mov     rdi, cs:pLanHead
0x1400042e7  mov     cs:hObjects, 0
0x1400042f2  test    rdi, rdi
0x1400042f5  jz      short loc_140004331
0x1400042f7  mov     rcx, [rdi+20h]; hMem
0x1400042fb  mov     rsi, [rdi+30h]
0x1400042ff  test    rcx, rcx
0x140004302  jz      short loc_140004316
0x140004304  mov     rbx, [rcx+10h]
0x140004308  call    cs:__imp_GlobalFree
0x14000430e  mov     rcx, rbx
0x140004311  test    rbx, rbx
0x140004314  jnz     short loc_140004304
0x140004316  lea     rcx, [rdi+40h]; lpCriticalSection
0x14000431a  call    cs:__imp_DeleteCriticalSection
0x140004320  mov     rcx, rdi; hMem
0x140004323  call    cs:__imp_GlobalFree
0x140004329  mov     rdi, rsi
0x14000432c  test    rsi, rsi
0x14000432f  jnz     short loc_1400042F7
0x140004331  mov     cs:pLanHead, 0
0x14000433c  mov     rcx, cs:WPP_GLOBAL_Control
0x140004343  cmp     rcx, rbp
0x140004346  jz      short loc_140004363
0x140004348  test    byte ptr [rcx+1Ch], 1
0x14000434c  jz      short loc_140004363
0x14000434e  mov     rcx, [rcx+10h]
0x140004352  lea     r8, WPP_90b53e51910230494b81f4a05de1546d_Traceguids
0x140004359  mov     edx, 48h ; 'H'
0x14000435e  call    WPP_SF_
0x140004363  add     rsp, 28h
0x140004367  pop     rdi
0x140004368  pop     rsi
0x140004369  pop     rbp
0x14000436a  pop     rbx
0x14000436b  retn
```
