# DeleteBoundaryFromInterface

- ea: `0x1800316d0`
- end: `0x180031856`
- name: `DeleteBoundaryFromInterface`
- size: `390`
- prototype: `__int64 __fastcall(LPVOID lpMem, LPVOID)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180034f44`
- `0x180035810`

## callees

- `0x18000ac60`
- `0x1800316d0`
- `0x18003a1c4`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800317bf`
- `KERNEL32!HeapFree` at `0x180031828`
- `KERNEL32!HeapFree` at `0x1800317bf`
- `KERNEL32!HeapFree` at `0x180031828`
- `WS2_32!__imp_closesocket` at `0x1800317d8`
- `WS2_32!__imp_closesocket` at `0x1800317d8`

## string_xrefs

- `0x180031755`: `DeleteBoundaryFromInterface: If %x Scope %d.%d.%d.%d/%d`

## pseudocode

```c
int __fastcall DeleteBoundaryFromInterface(_QWORD *lpMem, _QWORD *a2)
{
  __int64 v4; // rcx
  int v5; // r10d
  unsigned __int8 *v6; // rax
  _QWORD *v7; // rcx
  LPVOID *v8; // rax
  HANDLE v9; // rcx
  _QWORD *v10; // rax
  SOCKET v11; // rcx
  __int64 v12; // rcx
  _QWORD *v13; // rax
  __int64 v14; // rdx
  _QWORD *v15; // rcx
  int v17; // [rsp+20h] [rbp-838h]
  int v18; // [rsp+28h] [rbp-830h]
  int v19; // [rsp+30h] [rbp-828h]
  int v20; // [rsp+38h] [rbp-820h]
  int v21; // [rsp+40h] [rbp-818h] BYREF
  _BYTE v22[2044]; // [rsp+44h] [rbp-814h] BYREF

  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v4 = lpMem[2];
    LOWORD(v21) = 0;
    v5 = (unsigned __int8)MaskToMaskLen(*(unsigned int *)(v4 + 20));
    v6 = (unsigned __int8 *)lpMem[2];
    v20 = v5;
    v19 = v6[19];
    v18 = v6[18];
    v17 = v6[17];
    FormatRRASErrorString(
      &v21,
      L"DeleteBoundaryFromInterface: If %x Scope %d.%d.%d.%d/%d",
      *((unsigned int *)a2 + 8),
      v6[16],
      v17,
      v18,
      v19,
      v20);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v21);
  }
  v7 = (_QWORD *)*lpMem;
  if ( *(_QWORD **)(*lpMem + 8LL) != lpMem )
    goto LABEL_15;
  v8 = (LPVOID *)lpMem[1];
  if ( *v8 != lpMem )
    goto LABEL_15;
  *v8 = v7;
  v7[1] = v8;
  v9 = IPRouterHeap;
  --*(_DWORD *)(lpMem[2] + 24LL);
  HeapFree(v9, 0, lpMem);
  v10 = a2 + 5;
  if ( (_QWORD *)*v10 == v10 )
  {
    v11 = a2[7];
    if ( v11 != -1 )
    {
      closesocket(v11);
      a2[7] = -1;
    }
    v12 = *a2;
    if ( *(_QWORD **)(*a2 + 8LL) == a2 )
    {
      v13 = (_QWORD *)a2[1];
      if ( (_QWORD *)*v13 == a2 )
      {
        *v13 = v12;
        *(_QWORD *)(v12 + 8) = v13;
        v14 = a2[2];
        if ( *(_QWORD **)(v14 + 8) == a2 + 2 )
        {
          v15 = (_QWORD *)a2[3];
          if ( (_QWORD *)*v15 == a2 + 2 )
          {
            *v15 = v14;
            *(_QWORD *)(v14 + 8) = v15;
            LODWORD(v10) = HeapFree(IPRouterHeap, 0, a2);
            return (int)v10;
          }
        }
      }
    }
LABEL_15:
    __fastfail(3u);
  }
  return (int)v10;
}

```

## disassembly

```asm
0x1800316d0  mov     [rsp+arg_10], rbx
0x1800316d5  push    rdi
0x1800316d6  sub     rsp, 850h
0x1800316dd  mov     rax, cs:__security_cookie
0x1800316e4  xor     rax, rsp
0x1800316e7  mov     [rsp+858h+var_18], rax
0x1800316ef  mov     rbx, rdx
0x1800316f2  mov     rdi, rcx
0x1800316f5  xor     eax, eax
0x1800316f7  lea     rcx, [rsp+858h+var_814]; void *
0x1800316fc  xor     edx, edx; Val
0x1800316fe  mov     [rsp+858h+var_818], eax
0x180031702  mov     r8d, 7FCh; Size
0x180031708  call    memset_0
0x18003170d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180031714  jge     short loc_18003178B
0x180031716  mov     rcx, [rdi+10h]
0x18003171a  xor     eax, eax
0x18003171c  mov     word ptr [rsp+858h+var_818], ax
0x180031721  mov     ecx, [rcx+14h]
0x180031724  call    MaskToMaskLen
0x180031729  movzx   r10d, al
0x18003172d  mov     rax, [rdi+10h]
0x180031731  mov     [rsp+858h+var_820], r10d
0x180031736  movzx   ecx, byte ptr [rax+13h]
0x18003173a  movzx   edx, byte ptr [rax+12h]
0x18003173e  movzx   r8d, byte ptr [rax+11h]
0x180031743  movzx   r9d, byte ptr [rax+10h]
0x180031748  mov     [rsp+858h+var_828], ecx
0x18003174c  lea     rcx, [rsp+858h+var_818]
0x180031751  mov     [rsp+858h+var_830], edx
0x180031755  lea     rdx, aDeleteboundary; "DeleteBoundaryFromInterface: If %x Scop"...
0x18003175c  mov     [rsp+858h+var_838], r8d
0x180031761  mov     r8d, [rbx+20h]
0x180031765  call    FormatRRASErrorString
0x18003176a  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180031771  jge     short loc_18003178B
0x180031773  lea     r8, [rsp+858h+var_818]
0x180031778  lea     rdx, RasRtrmgrTraceInfo
0x18003177f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180031786  call    McTemplateU0z_EventWriteTransfer
0x18003178b  mov     rcx, [rdi]
0x18003178e  cmp     [rcx+8], rdi
0x180031792  jnz     loc_18003184F
0x180031798  mov     rax, [rdi+8]
0x18003179c  cmp     [rax], rdi
0x18003179f  jnz     loc_18003184F
0x1800317a5  mov     [rax], rcx
0x1800317a8  mov     r8, rdi; lpMem
0x1800317ab  mov     [rcx+8], rax
0x1800317af  xor     edx, edx; dwFlags
0x1800317b1  mov     rax, [rdi+10h]
0x1800317b5  mov     rcx, cs:IPRouterHeap; hHeap
0x1800317bc  dec     dword ptr [rax+18h]
0x1800317bf  call    cs:__imp_HeapFree
0x1800317c5  lea     rax, [rbx+28h]
0x1800317c9  cmp     [rax], rax
0x1800317cc  jnz     short loc_18003182E
0x1800317ce  mov     rcx, [rbx+38h]; s
0x1800317d2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800317d6  jz      short loc_1800317E6
0x1800317d8  call    cs:__imp_closesocket
0x1800317de  mov     qword ptr [rbx+38h], 0FFFFFFFFFFFFFFFFh
0x1800317e6  mov     rcx, [rbx]
0x1800317e9  cmp     [rcx+8], rbx
0x1800317ed  jnz     short loc_18003184F
0x1800317ef  mov     rax, [rbx+8]
0x1800317f3  cmp     [rax], rbx
0x1800317f6  jnz     short loc_18003184F
0x1800317f8  mov     [rax], rcx
0x1800317fb  mov     [rcx+8], rax
0x1800317ff  lea     rax, [rbx+10h]
0x180031803  mov     rdx, [rax]
0x180031806  cmp     [rdx+8], rax
0x18003180a  jnz     short loc_18003184F
0x18003180c  mov     rcx, [rax+8]
0x180031810  cmp     [rcx], rax
0x180031813  jnz     short loc_18003184F
0x180031815  mov     [rcx], rdx
0x180031818  mov     r8, rbx; lpMem
0x18003181b  mov     [rdx+8], rcx
0x18003181f  xor     edx, edx; dwFlags
0x180031821  mov     rcx, cs:IPRouterHeap; hHeap
0x180031828  call    cs:__imp_HeapFree
0x18003182e  mov     rcx, [rsp+858h+var_18]
0x180031836  xor     rcx, rsp; StackCookie
0x180031839  call    __security_check_cookie
0x18003183e  mov     rbx, [rsp+858h+arg_10]
0x180031846  add     rsp, 850h
0x18003184d  pop     rdi
0x18003184e  retn
0x18003184f  mov     ecx, 3
0x180031854  int     29h; Win8: RtlFailFast(ecx)
```
