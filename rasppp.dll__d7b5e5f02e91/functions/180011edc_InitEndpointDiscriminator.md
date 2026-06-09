# InitEndpointDiscriminator

- ea: `0x180011edc`
- end: `0x1800120fd`
- name: `InitEndpointDiscriminator`
- size: `545`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800046e0`

## callees

- `0x180001460`
- `0x180011edc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180011f96`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180011fad`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180011f96`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180011fad`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x180012070`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x180012070`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x180012064`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x180012064`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180012056`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180012056`
- `RPCRT4!UuidCreate` at `0x180012015`
- `RPCRT4!UuidCreate` at `0x180012015`
- `netutils!NetApiBufferFree` at `0x180011fed`
- `netutils!NetApiBufferFree` at `0x180012002`
- `netutils!NetApiBufferFree` at `0x180011fed`
- `netutils!NetApiBufferFree` at `0x180012002`
- `wkscli!NetWkstaTransportEnum` at `0x180011f4a`
- `wkscli!NetWkstaTransportEnum` at `0x180011f4a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameA` at `0x180012042`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameA` at `0x180012042`

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
0x180011edc  push    rbp
0x180011ede  push    rbx
0x180011edf  push    rsi
0x180011ee0  push    rdi
0x180011ee1  push    r14
0x180011ee3  push    r15
0x180011ee5  mov     rbp, rsp
0x180011ee8  sub     rsp, 78h
0x180011eec  mov     rax, cs:__security_cookie
0x180011ef3  xor     rax, rsp
0x180011ef6  mov     [rbp+var_10], rax
0x180011efa  lea     rax, [rbp+var_28]
0x180011efe  mov     [rsp+78h+resume_handle], 0; resume_handle
0x180011f07  mov     [rsp+78h+totalentries], rax; totalentries
0x180011f0c  lea     r8, [rbp+bufptr]; bufptr
0x180011f10  lea     rax, [rbp+var_38]
0x180011f14  mov     [rbp+var_38], 0
0x180011f1b  mov     rsi, rcx
0x180011f1e  mov     [rsp+78h+entriesread], rax; entriesread
0x180011f23  xorps   xmm0, xmm0
0x180011f26  mov     [rbp+var_28], 0
0x180011f2d  or      ebx, 0FFFFFFFFh
0x180011f30  mov     [rbp+nSize], 0
0x180011f37  mov     r9d, ebx; prefmaxlen
0x180011f3a  mov     [rbp+bufptr], 0
0x180011f42  xor     edx, edx; level
0x180011f44  xor     ecx, ecx; servername
0x180011f46  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x180011f4a  call    cs:__imp_NetWkstaTransportEnum
0x180011f51  nop     dword ptr [rax+rax+00h]
0x180011f56  test    eax, eax
0x180011f58  jnz     loc_18001200E
0x180011f5e  mov     ecx, [rbp+var_38]
0x180011f61  test    ecx, ecx
0x180011f63  jz      loc_180011FFE
0x180011f69  mov     rdx, [rbp+bufptr]
0x180011f6d  mov     eax, ecx
0x180011f6f  add     ecx, ebx
0x180011f71  mov     [rbp+var_38], ecx
0x180011f74  test    eax, eax
0x180011f76  jz      loc_180011FFE
0x180011f7c  cmp     dword ptr [rdx+18h], 0
0x180011f80  jz      short loc_180011F88
0x180011f82  add     rdx, 20h ; ' '
0x180011f86  jmp     short loc_180011F6D
0x180011f88  mov     byte ptr [rsi], 3
0x180011f8b  xor     r15d, r15d
0x180011f8e  mov     r14, [rdx+10h]
0x180011f92  movzx   ecx, word ptr [r14]
0x180011f96  call    cs:__imp__o_iswalpha
0x180011f9d  nop     dword ptr [rax+rax+00h]
0x180011fa2  movzx   ecx, word ptr [r14+2]
0x180011fa7  mov     edi, eax
0x180011fa9  movzx   ebx, word ptr [r14]
0x180011fad  call    cs:__imp__o_iswalpha
0x180011fb4  nop     dword ptr [rax+rax+00h]
0x180011fb9  inc     r15d
0x180011fbc  movzx   ecx, bl
0x180011fbf  sub     bl, 37h ; '7'
0x180011fc2  lea     r14, [r14+4]
0x180011fc6  test    edi, edi
0x180011fc8  movzx   edx, bl
0x180011fcb  cmovz   edx, ecx
0x180011fce  shl     dl, 4
0x180011fd1  neg     eax
0x180011fd3  sbb     al, al
0x180011fd5  and     al, 7
0x180011fd7  add     al, 30h ; '0'
0x180011fd9  sub     dl, al
0x180011fdb  add     dl, [r14-2]
0x180011fdf  mov     [r15+rsi], dl
0x180011fe3  cmp     r15d, 6
0x180011fe7  jb      short loc_180011F92
0x180011fe9  mov     rcx, [rbp+bufptr]; Buffer
0x180011fed  call    cs:__imp_NetApiBufferFree
0x180011ff4  nop     dword ptr [rax+rax+00h]
0x180011ff9  jmp     loc_1800120E1
0x180011ffe  mov     rcx, [rbp+bufptr]; Buffer
0x180012002  call    cs:__imp_NetApiBufferFree
0x180012009  nop     dword ptr [rax+rax+00h]
0x18001200e  lea     rcx, [rbp+Uuid]; Uuid
0x180012012  mov     byte ptr [rsi], 1
0x180012015  call    cs:__imp_UuidCreate
0x18001201c  nop     dword ptr [rax+rax+00h]
0x180012021  cmp     eax, 6CBh
0x180012026  jz      short loc_180012099
0x180012028  test    eax, eax
0x18001202a  jz      short loc_180012099
0x18001202c  cmp     eax, 720h
0x180012031  jz      short loc_180012099
0x180012033  lea     rdx, [rbp+nSize]; nSize
0x180012037  mov     [rbp+nSize], 14h
0x18001203e  lea     rcx, [rsi+1]; lpBuffer
0x180012042  call    cs:__imp_GetComputerNameA
0x180012049  nop     dword ptr [rax+rax+00h]
0x18001204e  test    eax, eax
0x180012050  jnz     loc_1800120E1
0x180012056  call    cs:__imp_GetTickCount
0x18001205d  nop     dword ptr [rax+rax+00h]
0x180012062  mov     ecx, eax
0x180012064  call    cs:__imp__o_srand
0x18001206b  nop     dword ptr [rax+rax+00h]
0x180012070  call    cs:__imp_rand
0x180012077  nop     dword ptr [rax+rax+00h]
0x18001207c  mov     ecx, eax
0x18001207e  mov     [rsi+4], al
0x180012081  shr     ecx, 18h
0x180012084  mov     [rsi+1], cl
0x180012087  mov     ecx, eax
0x180012089  shr     ecx, 10h
0x18001208c  mov     [rsi+2], cl
0x18001208f  mov     ecx, eax
0x180012091  shr     ecx, 8
0x180012094  mov     [rsi+3], cl
0x180012097  jmp     short loc_1800120E1
0x180012099  mov     ecx, [rbp+Uuid.Data1]
0x18001209c  mov     eax, ecx
0x18001209e  shr     eax, 18h
0x1800120a1  mov     [rsi+1], al
0x1800120a4  mov     eax, ecx
0x1800120a6  shr     eax, 10h
0x1800120a9  mov     [rsi+2], al
0x1800120ac  mov     eax, ecx
0x1800120ae  mov     [rsi+4], cl
0x1800120b1  movzx   ecx, [rbp+Uuid.Data2]
0x1800120b5  shr     eax, 8
0x1800120b8  mov     [rsi+3], al
0x1800120bb  movzx   eax, cx
0x1800120be  shr     ax, 8
0x1800120c2  mov     [rsi+5], al
0x1800120c5  mov     [rsi+6], cl
0x1800120c8  movzx   ecx, [rbp+Uuid.Data3]
0x1800120cc  movzx   eax, cx
0x1800120cf  mov     [rsi+8], cl
0x1800120d2  shr     ax, 8
0x1800120d6  mov     [rsi+7], al
0x1800120d9  mov     rax, qword ptr [rbp+Uuid.Data4]
0x1800120dd  mov     [rsi+9], rax
0x1800120e1  xor     eax, eax
0x1800120e3  mov     rcx, [rbp+var_10]
0x1800120e7  xor     rcx, rsp; StackCookie
0x1800120ea  call    __security_check_cookie
0x1800120ef  add     rsp, 78h
0x1800120f3  pop     r15
0x1800120f5  pop     r14
0x1800120f7  pop     rdi
0x1800120f8  pop     rsi
0x1800120f9  pop     rbx
0x1800120fa  pop     rbp
0x1800120fb  retn
```
