# RemoveFromTimerQ

- ea: `0x18000f984`
- end: `0x18000faf5`
- name: `RemoveFromTimerQ`
- size: `369`
- prototype: ``
- caller_count: `19`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800022e4`
- `0x1800043a8`
- `0x180009cd0`
- `0x180009fd0`
- `0x18000a280`
- `0x18000b2e8`
- `0x18000b580`
- `0x18000b720`
- `0x18000be68`
- `0x18000c050`
- `0x18000c3e8`
- `0x18000e540`
- `0x18000e7a4`
- `0x18000ecac`
- `0x180013c48`
- `0x18001427c`
- `0x180015a80`
- `0x180015d28`
- `0x180017cf0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x18000f984`
- `0x18002b0dc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000faca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000faca`

## string_xrefs

- `0x18000f9e2`: `RemoveFromTimerQ called portid=%d,Id=%d,Protocol=%x,EventType=%d,fAuth=%d`

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
  if ( (byte_18004DF34 & 1) != 0 )
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
    if ( (byte_18004DF34 & 1) != 0 )
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
0x18000f984  push    rbx
0x18000f986  push    rbp
0x18000f987  push    rsi
0x18000f988  push    rdi
0x18000f989  push    r14
0x18000f98b  sub     rsp, 850h
0x18000f992  mov     rax, cs:__security_cookie
0x18000f999  xor     rax, rsp
0x18000f99c  mov     [rsp+878h+var_38], rax
0x18000f9a4  mov     edi, r8d
0x18000f9a7  mov     ebx, edx
0x18000f9a9  mov     ebp, ecx
0x18000f9ab  xor     eax, eax
0x18000f9ad  xor     edx, edx; Val
0x18000f9af  mov     [rsp+878h+var_838], eax
0x18000f9b3  mov     r8d, 7FCh; Size
0x18000f9b9  lea     rcx, [rsp+878h+var_834]; void *
0x18000f9be  mov     esi, r9d
0x18000f9c1  call    memset_0
0x18000f9c6  test    cs:byte_18004DF34, 1
0x18000f9cd  mov     r14d, [rsp+878h+arg_20]
0x18000f9d5  jz      short loc_18000FA23
0x18000f9d7  xor     eax, eax
0x18000f9d9  mov     [rsp+878h+var_848], esi
0x18000f9dd  mov     [rsp+878h+var_850], r14d
0x18000f9e2  lea     rdx, aRemovefromtime; "RemoveFromTimerQ called portid=%d,Id=%d"...
0x18000f9e9  mov     r9d, ebx
0x18000f9ec  mov     word ptr [rsp+878h+var_838], ax
0x18000f9f1  mov     r8d, ebp
0x18000f9f4  mov     [rsp+878h+var_858], edi
0x18000f9f8  lea     rcx, [rsp+878h+var_838]
0x18000f9fd  call    FormatRRASErrorString
0x18000fa02  test    cs:byte_18004DF34, 1
0x18000fa09  jz      short loc_18000FA23
0x18000fa0b  lea     r8, [rsp+878h+var_838]
0x18000fa10  lea     rdx, RasPppTraceInfo
0x18000fa17  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000fa1e  call    McTemplateU0z_EventWriteTransfer
0x18000fa23  mov     rax, qword ptr cs:TimerQ
0x18000fa2a  mov     r8, rax
0x18000fa2d  test    rax, rax
0x18000fa30  jz      loc_18000FAD6
0x18000fa36  cmp     [r8+10h], r14d
0x18000fa3a  jnz     short loc_18000FA5B
0x18000fa3c  cmp     [r8+14h], ebp
0x18000fa40  jnz     short loc_18000FA5B
0x18000fa42  cmp     dword ptr [r8+10h], 0
0x18000fa47  jnz     short loc_18000FA63
0x18000fa49  cmp     [r8+24h], ebx
0x18000fa4d  jnz     short loc_18000FA5B
0x18000fa4f  cmp     [r8+20h], edi
0x18000fa53  jnz     short loc_18000FA5B
0x18000fa55  cmp     [r8+28h], esi
0x18000fa59  jz      short loc_18000FA63
0x18000fa5b  mov     r8, [r8]; lpMem
0x18000fa5e  test    r8, r8
0x18000fa61  jnz     short loc_18000FA36
0x18000fa63  test    r8, r8
0x18000fa66  jz      short loc_18000FAD6
0x18000fa68  cmp     r8, rax
0x18000fa6b  jnz     short loc_18000FA94
0x18000fa6d  mov     rax, [r8]
0x18000fa70  mov     qword ptr cs:TimerQ, rax
0x18000fa77  test    rax, rax
0x18000fa7a  jz      short loc_18000FAC1
0x18000fa7c  mov     qword ptr [rax+8], 0
0x18000fa84  mov     rcx, qword ptr cs:TimerQ
0x18000fa8b  mov     eax, [r8+2Ch]
0x18000fa8f  add     [rcx+2Ch], eax
0x18000fa92  jmp     short loc_18000FAC1
0x18000fa94  mov     rcx, [r8]
0x18000fa97  test    rcx, rcx
0x18000fa9a  jnz     short loc_18000FAA5
0x18000fa9c  mov     rax, [r8+8]
0x18000faa0  mov     [rax], rcx
0x18000faa3  jmp     short loc_18000FAC1
0x18000faa5  mov     eax, [r8+2Ch]
0x18000faa9  add     [rcx+2Ch], eax
0x18000faac  mov     rcx, [r8+8]
0x18000fab0  mov     rax, [r8]
0x18000fab3  mov     [rcx], rax
0x18000fab6  mov     rcx, [r8]
0x18000fab9  mov     rax, [r8+8]
0x18000fabd  mov     [rcx+8], rax
0x18000fac1  mov     rcx, cs:hHeap; hHeap
0x18000fac8  xor     edx, edx; dwFlags
0x18000faca  call    cs:__imp_HeapFree
0x18000fad1  nop     dword ptr [rax+rax+00h]
0x18000fad6  mov     rcx, [rsp+878h+var_38]
0x18000fade  xor     rcx, rsp; StackCookie
0x18000fae1  call    __security_check_cookie
0x18000fae6  add     rsp, 850h
0x18000faed  pop     r14
0x18000faef  pop     rdi
0x18000faf0  pop     rsi
0x18000faf1  pop     rbp
0x18000faf2  pop     rbx
0x18000faf3  retn
```
