# InitEndpointDiscriminator

- ea: `0x180011928`
- end: `0x180011b00`
- name: `InitEndpointDiscriminator`
- size: `472`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004630`

## callees

- `0x180001460`
- `0x180011928`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x1800119d4`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x1800119e5`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x1800119d4`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x1800119e5`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x180011a7a`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x180011a7a`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x180011a74`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x180011a74`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180011a6c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180011a6c`
- `RPCRT4!UuidCreate` at `0x180011a3b`
- `RPCRT4!UuidCreate` at `0x180011a3b`
- `netutils!NetApiBufferFree` at `0x180011a1f`
- `netutils!NetApiBufferFree` at `0x180011a2e`
- `netutils!NetApiBufferFree` at `0x180011a1f`
- `netutils!NetApiBufferFree` at `0x180011a2e`
- `wkscli!NetWkstaTransportEnum` at `0x180011996`
- `wkscli!NetWkstaTransportEnum` at `0x180011996`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameA` at `0x180011a62`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameA` at `0x180011a62`

## pseudocode

```c
__int64 __fastcall InitEndpointDiscriminator(__int64 a1)
{
  DWORD v2; // ecx
  LPBYTE i; // rdx
  DWORD v4; // eax
  __int64 v5; // r15
  unsigned __int16 *v6; // r14
  int v7; // edi
  __int16 v8; // bx
  int v9; // eax
  char v10; // dl
  RPC_STATUS v11; // eax
  DWORD TickCount; // eax
  int v13; // eax
  unsigned int Data1; // ecx
  char v15; // ah
  DWORD entriesread; // [rsp+40h] [rbp-38h] BYREF
  DWORD nSize; // [rsp+44h] [rbp-34h] BYREF
  LPBYTE bufptr; // [rsp+48h] [rbp-30h] BYREF
  DWORD totalentries; // [rsp+50h] [rbp-28h] BYREF
  UUID Uuid; // [rsp+58h] [rbp-20h] BYREF

  entriesread = 0;
  totalentries = 0;
  nSize = 0;
  bufptr = 0;
  Uuid = 0;
  if ( !NetWkstaTransportEnum(0, 0, &bufptr, 0xFFFFFFFF, &entriesread, &totalentries, 0) )
  {
    v2 = entriesread;
    if ( entriesread )
    {
      for ( i = bufptr; ; i += 32 )
      {
        v4 = v2--;
        entriesread = v2;
        if ( !v4 )
          break;
        if ( !*((_DWORD *)i + 6) )
        {
          *(_BYTE *)a1 = 3;
          LODWORD(v5) = 0;
          v6 = (unsigned __int16 *)*((_QWORD *)i + 2);
          do
          {
            v7 = _o_iswalpha(*v6);
            v8 = *v6;
            v9 = _o_iswalpha(v6[1]);
            v5 = (unsigned int)(v5 + 1);
            v6 += 2;
            v10 = v8 - 55;
            if ( !v7 )
              v10 = v8;
            *(_BYTE *)(v5 + a1) = *((_BYTE *)v6 - 2) + 16 * v10 - (v9 != 0 ? 55 : 48);
          }
          while ( (unsigned int)v5 < 6 );
          NetApiBufferFree(bufptr);
          return 0;
        }
      }
    }
    NetApiBufferFree(bufptr);
  }
  *(_BYTE *)a1 = 1;
  v11 = UuidCreate(&Uuid);
  if ( v11 == 1739 || !v11 || v11 == 1824 )
  {
    Data1 = Uuid.Data1;
    *(_BYTE *)(a1 + 1) = HIBYTE(Uuid.Data1);
    *(_BYTE *)(a1 + 2) = BYTE2(Data1);
    v15 = BYTE1(Data1);
    *(_BYTE *)(a1 + 4) = Data1;
    LOWORD(Data1) = Uuid.Data2;
    *(_BYTE *)(a1 + 3) = v15;
    *(_BYTE *)(a1 + 5) = BYTE1(Data1);
    *(_BYTE *)(a1 + 6) = Data1;
    BYTE1(Data1) = HIBYTE(Uuid.Data3);
    *(_BYTE *)(a1 + 8) = Uuid.Data3;
    *(_BYTE *)(a1 + 7) = BYTE1(Data1);
    *(_QWORD *)(a1 + 9) = *(_QWORD *)Uuid.Data4;
  }
  else
  {
    nSize = 20;
    if ( !GetComputerNameA((LPSTR)(a1 + 1), &nSize) )
    {
      TickCount = GetTickCount();
      _o_srand(TickCount);
      v13 = rand();
      *(_BYTE *)(a1 + 4) = v13;
      *(_BYTE *)(a1 + 1) = HIBYTE(v13);
      *(_BYTE *)(a1 + 2) = BYTE2(v13);
      *(_BYTE *)(a1 + 3) = BYTE1(v13);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180011928  push    rbp
0x18001192a  push    rbx
0x18001192b  push    rsi
0x18001192c  push    rdi
0x18001192d  push    r14
0x18001192f  push    r15
0x180011931  mov     rbp, rsp
0x180011934  sub     rsp, 78h
0x180011938  mov     rax, cs:__security_cookie
0x18001193f  xor     rax, rsp
0x180011942  mov     [rbp+var_10], rax
0x180011946  lea     rax, [rbp+var_28]
0x18001194a  mov     [rsp+78h+resume_handle], 0; resume_handle
0x180011953  mov     [rsp+78h+totalentries], rax; totalentries
0x180011958  lea     r8, [rbp+bufptr]; bufptr
0x18001195c  lea     rax, [rbp+var_38]
0x180011960  mov     [rbp+var_38], 0
0x180011967  mov     rsi, rcx
0x18001196a  mov     [rsp+78h+entriesread], rax; entriesread
0x18001196f  xorps   xmm0, xmm0
0x180011972  mov     [rbp+var_28], 0
0x180011979  or      ebx, 0FFFFFFFFh
0x18001197c  mov     [rbp+nSize], 0
0x180011983  mov     r9d, ebx; prefmaxlen
0x180011986  mov     [rbp+bufptr], 0
0x18001198e  xor     edx, edx; level
0x180011990  xor     ecx, ecx; servername
0x180011992  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x180011996  call    cs:__imp_NetWkstaTransportEnum
0x18001199c  test    eax, eax
0x18001199e  jnz     loc_180011A34
0x1800119a4  mov     ecx, [rbp+var_38]
0x1800119a7  test    ecx, ecx
0x1800119a9  jz      short loc_180011A2A
0x1800119ab  mov     rdx, [rbp+bufptr]
0x1800119af  mov     eax, ecx
0x1800119b1  add     ecx, ebx
0x1800119b3  mov     [rbp+var_38], ecx
0x1800119b6  test    eax, eax
0x1800119b8  jz      short loc_180011A2A
0x1800119ba  cmp     dword ptr [rdx+18h], 0
0x1800119be  jz      short loc_1800119C6
0x1800119c0  add     rdx, 20h ; ' '
0x1800119c4  jmp     short loc_1800119AF
0x1800119c6  mov     byte ptr [rsi], 3
0x1800119c9  xor     r15d, r15d
0x1800119cc  mov     r14, [rdx+10h]
0x1800119d0  movzx   ecx, word ptr [r14]
0x1800119d4  call    cs:__imp__o_iswalpha
0x1800119da  movzx   ecx, word ptr [r14+2]
0x1800119df  mov     edi, eax
0x1800119e1  movzx   ebx, word ptr [r14]
0x1800119e5  call    cs:__imp__o_iswalpha
0x1800119eb  inc     r15d
0x1800119ee  movzx   ecx, bl
0x1800119f1  sub     bl, 37h ; '7'
0x1800119f4  lea     r14, [r14+4]
0x1800119f8  test    edi, edi
0x1800119fa  movzx   edx, bl
0x1800119fd  cmovz   edx, ecx
0x180011a00  shl     dl, 4
0x180011a03  neg     eax
0x180011a05  sbb     al, al
0x180011a07  and     al, 7
0x180011a09  add     al, 30h ; '0'
0x180011a0b  sub     dl, al
0x180011a0d  add     dl, [r14-2]
0x180011a11  mov     [r15+rsi], dl
0x180011a15  cmp     r15d, 6
0x180011a19  jb      short loc_1800119D0
0x180011a1b  mov     rcx, [rbp+bufptr]; Buffer
0x180011a1f  call    cs:__imp_NetApiBufferFree
0x180011a25  jmp     loc_180011AE5
0x180011a2a  mov     rcx, [rbp+bufptr]; Buffer
0x180011a2e  call    cs:__imp_NetApiBufferFree
0x180011a34  lea     rcx, [rbp+Uuid]; Uuid
0x180011a38  mov     byte ptr [rsi], 1
0x180011a3b  call    cs:__imp_UuidCreate
0x180011a41  cmp     eax, 6CBh
0x180011a46  jz      short loc_180011A9D
0x180011a48  test    eax, eax
0x180011a4a  jz      short loc_180011A9D
0x180011a4c  cmp     eax, 720h
0x180011a51  jz      short loc_180011A9D
0x180011a53  lea     rdx, [rbp+nSize]; nSize
0x180011a57  mov     [rbp+nSize], 14h
0x180011a5e  lea     rcx, [rsi+1]; lpBuffer
0x180011a62  call    cs:__imp_GetComputerNameA
0x180011a68  test    eax, eax
0x180011a6a  jnz     short loc_180011AE5
0x180011a6c  call    cs:__imp_GetTickCount
0x180011a72  mov     ecx, eax
0x180011a74  call    cs:__imp__o_srand
0x180011a7a  call    cs:__imp_rand
0x180011a80  mov     ecx, eax
0x180011a82  mov     [rsi+4], al
0x180011a85  shr     ecx, 18h
0x180011a88  mov     [rsi+1], cl
0x180011a8b  mov     ecx, eax
0x180011a8d  shr     ecx, 10h
0x180011a90  mov     [rsi+2], cl
0x180011a93  mov     ecx, eax
0x180011a95  shr     ecx, 8
0x180011a98  mov     [rsi+3], cl
0x180011a9b  jmp     short loc_180011AE5
0x180011a9d  mov     ecx, [rbp+Uuid.Data1]
0x180011aa0  mov     eax, ecx
0x180011aa2  shr     eax, 18h
0x180011aa5  mov     [rsi+1], al
0x180011aa8  mov     eax, ecx
0x180011aaa  shr     eax, 10h
0x180011aad  mov     [rsi+2], al
0x180011ab0  mov     eax, ecx
0x180011ab2  mov     [rsi+4], cl
0x180011ab5  movzx   ecx, [rbp+Uuid.Data2]
0x180011ab9  shr     eax, 8
0x180011abc  mov     [rsi+3], al
0x180011abf  movzx   eax, cx
0x180011ac2  shr     ax, 8
0x180011ac6  mov     [rsi+5], al
0x180011ac9  mov     [rsi+6], cl
0x180011acc  movzx   ecx, [rbp+Uuid.Data3]
0x180011ad0  movzx   eax, cx
0x180011ad3  mov     [rsi+8], cl
0x180011ad6  shr     ax, 8
0x180011ada  mov     [rsi+7], al
0x180011add  mov     rax, qword ptr [rbp+Uuid.Data4]
0x180011ae1  mov     [rsi+9], rax
0x180011ae5  xor     eax, eax
0x180011ae7  mov     rcx, [rbp+var_10]
0x180011aeb  xor     rcx, rsp; StackCookie
0x180011aee  call    __security_check_cookie
0x180011af3  add     rsp, 78h
0x180011af7  pop     r15
0x180011af9  pop     r14
0x180011afb  pop     rdi
0x180011afc  pop     rsi
0x180011afd  pop     rbx
0x180011afe  pop     rbp
0x180011aff  retn
```
