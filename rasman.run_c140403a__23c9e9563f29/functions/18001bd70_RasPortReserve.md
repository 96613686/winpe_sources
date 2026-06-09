# RasPortReserve

- ea: `0x18001bd70`
- end: `0x18001be7f`
- name: `RasPortReserve`
- size: `271`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180002f80`
- `0x18001bd70`
- `0x180020fd8`
- `0x180021000`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001bdb4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001bdb4`

## pseudocode

```c
__int64 __fastcall RasPortReserve(__int64 a1, __int64 a2)
{
  DWORD CurrentProcessId; // eax
  DWORD v5; // ebx
  unsigned int v6; // eax
  unsigned int v7; // ebx
  PVOID *v8; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  CurrentProcessId = GetCurrentProcessId();
  v5 = CurrentProcessId;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      102,
      &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids,
      CurrentProcessId);
  }
  v6 = SubmitLocalRequest(1u, a1, 0, v5, 0, a2);
  v7 = v6;
  if ( !v6 )
    goto LABEL_14;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v7;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v6);
LABEL_14:
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x40) != 0 && *((_BYTE *)v8 + 25) >= 6u )
    WPP_SF_d(v8[2], 104, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x18001bd70  push    rbx
0x18001bd72  push    rsi
0x18001bd73  push    rdi
0x18001bd74  push    r14
0x18001bd76  sub     rsp, 38h
0x18001bd7a  mov     rdi, rdx
0x18001bd7d  mov     rsi, rcx
0x18001bd80  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd87  lea     r14, WPP_GLOBAL_Control
0x18001bd8e  cmp     rcx, r14
0x18001bd91  jz      short loc_18001BDB4
0x18001bd93  test    byte ptr [rcx+1Ch], 40h
0x18001bd97  jz      short loc_18001BDB4
0x18001bd99  cmp     byte ptr [rcx+19h], 6
0x18001bd9d  jb      short loc_18001BDB4
0x18001bd9f  mov     rcx, [rcx+10h]
0x18001bda3  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001bdaa  mov     edx, 65h ; 'e'
0x18001bdaf  call    WPP_SF_
0x18001bdb4  call    cs:__imp_GetCurrentProcessId
0x18001bdba  mov     ebx, eax
0x18001bdbc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bdc3  cmp     rcx, r14
0x18001bdc6  jz      short loc_18001BDEC
0x18001bdc8  test    byte ptr [rcx+1Ch], 40h
0x18001bdcc  jz      short loc_18001BDEC
0x18001bdce  cmp     byte ptr [rcx+19h], 5
0x18001bdd2  jb      short loc_18001BDEC
0x18001bdd4  mov     rcx, [rcx+10h]
0x18001bdd8  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001bddf  mov     edx, 66h ; 'f'
0x18001bde4  mov     r9d, eax
0x18001bde7  call    WPP_SF_d
0x18001bdec  mov     ecx, 1
0x18001bdf1  mov     [rsp+58h+var_30], rdi
0x18001bdf6  mov     r9d, ebx
0x18001bdf9  mov     [rsp+58h+var_38], 0
0x18001be02  xor     r8d, r8d
0x18001be05  mov     rdx, rsi
0x18001be08  call    SubmitLocalRequest
0x18001be0d  mov     ebx, eax
0x18001be0f  test    eax, eax
0x18001be11  jz      short loc_18001BE43
0x18001be13  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be1a  cmp     rcx, r14
0x18001be1d  jz      short loc_18001BE73
0x18001be1f  test    byte ptr [rcx+1Ch], 40h
0x18001be23  jz      short loc_18001BE4A
0x18001be25  cmp     byte ptr [rcx+19h], 2
0x18001be29  jb      short loc_18001BE4A
0x18001be2b  mov     rcx, [rcx+10h]
0x18001be2f  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001be36  mov     edx, 67h ; 'g'
0x18001be3b  mov     r9d, eax
0x18001be3e  call    WPP_SF_d
0x18001be43  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be4a  cmp     rcx, r14
0x18001be4d  jz      short loc_18001BE73
0x18001be4f  test    byte ptr [rcx+1Ch], 40h
0x18001be53  jz      short loc_18001BE73
0x18001be55  cmp     byte ptr [rcx+19h], 6
0x18001be59  jb      short loc_18001BE73
0x18001be5b  mov     rcx, [rcx+10h]
0x18001be5f  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001be66  mov     edx, 68h ; 'h'
0x18001be6b  mov     r9d, ebx
0x18001be6e  call    WPP_SF_d
0x18001be73  mov     eax, ebx
0x18001be75  add     rsp, 38h
0x18001be79  pop     r14
0x18001be7b  pop     rdi
0x18001be7c  pop     rsi
0x18001be7d  pop     rbx
0x18001be7e  retn
```
