# RemoveFromTimerQ

- ea: `0x18000f528`
- end: `0x18000f692`
- name: `RemoveFromTimerQ`
- size: `362`
- prototype: ``
- caller_count: `19`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800022cc`
- `0x180004304`
- `0x180009900`
- `0x180009c00`
- `0x180009eb0`
- `0x18000aed4`
- `0x18000b170`
- `0x18000b310`
- `0x18000ba40`
- `0x18000bc28`
- `0x18000bfc0`
- `0x18000e100`
- `0x18000e364`
- `0x18000e86c`
- `0x180013584`
- `0x180013bb4`
- `0x180015320`
- `0x1800155b8`
- `0x1800174e0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x18000f528`
- `0x18002a138`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f66e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f66e`

## string_xrefs

- `0x18000f586`: `RemoveFromTimerQ called portid=%d,Id=%d,Protocol=%x,EventType=%d,fAuth=%d`

## pseudocode

```c
int __fastcall RemoveFromTimerQ(unsigned int a1, unsigned int a2, int a3, int a4, int a5)
{
  int result; // eax
  _QWORD *v10; // r8
  _QWORD *v11; // rax
  int v12; // [rsp+40h] [rbp-838h] BYREF
  _BYTE v13[2044]; // [rsp+44h] [rbp-834h] BYREF

  v12 = 0;
  memset_0(v13, 0, sizeof(v13));
  if ( (byte_18004CF34 & 1) != 0 )
  {
    LOWORD(v12) = 0;
    FormatRRASErrorString(
      &v12,
      L"RemoveFromTimerQ called portid=%d,Id=%d,Protocol=%x,EventType=%d,fAuth=%d",
      a1,
      a2,
      a3,
      a5,
      a4);
    if ( (byte_18004CF34 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v12);
  }
  result = (int)TimerQ;
  v10 = TimerQ;
  if ( TimerQ )
  {
    do
    {
      if ( *((_DWORD *)v10 + 4) == a5
        && *((_DWORD *)v10 + 5) == a1
        && (*((_DWORD *)v10 + 4)
         || *((_DWORD *)v10 + 9) == a2 && *((_DWORD *)v10 + 8) == a3 && *((_DWORD *)v10 + 10) == a4) )
      {
        break;
      }
      v10 = (_QWORD *)*v10;
    }
    while ( v10 );
    if ( v10 )
    {
      if ( v10 == TimerQ )
      {
        v11 = (_QWORD *)*v10;
        TimerQ = v11;
        if ( v11 )
        {
          v11[1] = 0;
          *((_DWORD *)TimerQ + 11) += *((_DWORD *)v10 + 11);
        }
      }
      else if ( *v10 )
      {
        *(_DWORD *)(*v10 + 44LL) += *((_DWORD *)v10 + 11);
        *(_QWORD *)v10[1] = *v10;
        *(_QWORD *)(*v10 + 8LL) = v10[1];
      }
      else
      {
        *(_QWORD *)v10[1] = 0;
      }
      return HeapFree(hHeap, 0, v10);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000f528  push    rbx
0x18000f52a  push    rbp
0x18000f52b  push    rsi
0x18000f52c  push    rdi
0x18000f52d  push    r14
0x18000f52f  sub     rsp, 850h
0x18000f536  mov     rax, cs:__security_cookie
0x18000f53d  xor     rax, rsp
0x18000f540  mov     [rsp+878h+var_38], rax
0x18000f548  mov     edi, r8d
0x18000f54b  mov     ebx, edx
0x18000f54d  mov     ebp, ecx
0x18000f54f  xor     eax, eax
0x18000f551  xor     edx, edx; Val
0x18000f553  mov     [rsp+878h+var_838], eax
0x18000f557  mov     r8d, 7FCh; Size
0x18000f55d  lea     rcx, [rsp+878h+var_834]; void *
0x18000f562  mov     esi, r9d
0x18000f565  call    memset_0
0x18000f56a  test    cs:byte_18004CF34, 1
0x18000f571  mov     r14d, [rsp+878h+arg_20]
0x18000f579  jz      short loc_18000F5C7
0x18000f57b  xor     eax, eax
0x18000f57d  mov     [rsp+878h+var_848], esi
0x18000f581  mov     [rsp+878h+var_850], r14d
0x18000f586  lea     rdx, aRemovefromtime; "RemoveFromTimerQ called portid=%d,Id=%d"...
0x18000f58d  mov     r9d, ebx
0x18000f590  mov     word ptr [rsp+878h+var_838], ax
0x18000f595  mov     r8d, ebp
0x18000f598  mov     [rsp+878h+var_858], edi
0x18000f59c  lea     rcx, [rsp+878h+var_838]
0x18000f5a1  call    FormatRRASErrorString
0x18000f5a6  test    cs:byte_18004CF34, 1
0x18000f5ad  jz      short loc_18000F5C7
0x18000f5af  lea     r8, [rsp+878h+var_838]
0x18000f5b4  lea     rdx, RasPppTraceInfo
0x18000f5bb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000f5c2  call    McTemplateU0z_EventWriteTransfer
0x18000f5c7  mov     rax, qword ptr cs:TimerQ
0x18000f5ce  mov     r8, rax
0x18000f5d1  test    rax, rax
0x18000f5d4  jz      loc_18000F674
0x18000f5da  cmp     [r8+10h], r14d
0x18000f5de  jnz     short loc_18000F5FF
0x18000f5e0  cmp     [r8+14h], ebp
0x18000f5e4  jnz     short loc_18000F5FF
0x18000f5e6  cmp     dword ptr [r8+10h], 0
0x18000f5eb  jnz     short loc_18000F607
0x18000f5ed  cmp     [r8+24h], ebx
0x18000f5f1  jnz     short loc_18000F5FF
0x18000f5f3  cmp     [r8+20h], edi
0x18000f5f7  jnz     short loc_18000F5FF
0x18000f5f9  cmp     [r8+28h], esi
0x18000f5fd  jz      short loc_18000F607
0x18000f5ff  mov     r8, [r8]; lpMem
0x18000f602  test    r8, r8
0x18000f605  jnz     short loc_18000F5DA
0x18000f607  test    r8, r8
0x18000f60a  jz      short loc_18000F674
0x18000f60c  cmp     r8, rax
0x18000f60f  jnz     short loc_18000F638
0x18000f611  mov     rax, [r8]
0x18000f614  mov     qword ptr cs:TimerQ, rax
0x18000f61b  test    rax, rax
0x18000f61e  jz      short loc_18000F665
0x18000f620  mov     qword ptr [rax+8], 0
0x18000f628  mov     rcx, qword ptr cs:TimerQ
0x18000f62f  mov     eax, [r8+2Ch]
0x18000f633  add     [rcx+2Ch], eax
0x18000f636  jmp     short loc_18000F665
0x18000f638  mov     rcx, [r8]
0x18000f63b  test    rcx, rcx
0x18000f63e  jnz     short loc_18000F649
0x18000f640  mov     rax, [r8+8]
0x18000f644  mov     [rax], rcx
0x18000f647  jmp     short loc_18000F665
0x18000f649  mov     eax, [r8+2Ch]
0x18000f64d  add     [rcx+2Ch], eax
0x18000f650  mov     rcx, [r8+8]
0x18000f654  mov     rax, [r8]
0x18000f657  mov     [rcx], rax
0x18000f65a  mov     rcx, [r8]
0x18000f65d  mov     rax, [r8+8]
0x18000f661  mov     [rcx+8], rax
0x18000f665  mov     rcx, cs:hHeap; hHeap
0x18000f66c  xor     edx, edx; dwFlags
0x18000f66e  call    cs:__imp_HeapFree
0x18000f674  mov     rcx, [rsp+878h+var_38]
0x18000f67c  xor     rcx, rsp; StackCookie
0x18000f67f  call    __security_check_cookie
0x18000f684  add     rsp, 850h
0x18000f68b  pop     r14
0x18000f68d  pop     rdi
0x18000f68e  pop     rsi
0x18000f68f  pop     rbp
0x18000f690  pop     rbx
0x18000f691  retn
```
