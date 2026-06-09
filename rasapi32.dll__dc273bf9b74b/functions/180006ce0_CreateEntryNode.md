# CreateEntryNode

- ea: `0x180006ce0`
- end: `0x180007145`
- name: `CreateEntryNode`
- size: `1125`
- prototype: `char *__fastcall(int, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180021080`
- `0x180028050`
- `0x180029cd0`
- `0x18007c380`
- `0x1800d34e4`

## callees

- `0x1800064a0`
- `0x180006514`
- `0x180006ce0`
- `0x1800087b0`
- `0x18000ada0`
- `0x1800208ec`
- `0x180035340`
- `0x18004e984`
- `0x18007efdc`
- `0x1800ded06`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180006d12`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180006f25`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180006d12`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180006f25`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006f13`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006f13`
- `RPCRT4!UuidCreate` at `0x1800070ea`
- `RPCRT4!UuidCreate` at `0x1800070ea`

## pseudocode

```c
char *__fastcall CreateEntryNode(int a1, __int64 a2, __int64 a3, __int64 a4)
{
  char *v5; // rax
  char *v6; // rdi
  __int64 List; // rax
  __int64 v8; // rax
  UUID *v9; // rax
  __int64 LinkNode; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(a4) = a1 != 0;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_38cda081c674317ed40163d707084d83_Traceguids, a4);
  }
  v5 = (char *)GlobalAlloc(0x40u, 0x410u);
  v6 = v5;
  if ( !v5 )
    return 0;
  memset_0(v5, 0, 0x410u);
  *((_QWORD *)v6 + 2) = v6 + 32;
  List = DtlCreateList();
  *((_QWORD *)v6 + 8) = List;
  if ( !List )
    goto LABEL_18;
  if ( a1 )
  {
    LinkNode = CreateLinkNode();
    if ( !LinkNode )
      goto LABEL_18;
    DtlAddNodeLast(*((_QWORD *)v6 + 8), LinkNode);
  }
  *((_DWORD *)v6 + 8) = -1;
  *((_DWORD *)v6 + 14) = 1;
  *((_QWORD *)v6 + 9) = 1;
  *((_DWORD *)v6 + 20) = 1;
  *((_DWORD *)v6 + 36) = 1;
  *((_DWORD *)v6 + 39) = 1;
  *(_QWORD *)(v6 + 148) = 1;
  *((_DWORD *)v6 + 41) = 1;
  *(_QWORD *)(v6 + 212) = 1;
  *((_DWORD *)v6 + 68) = 1;
  *((_DWORD *)v6 + 69) = 1;
  *((_DWORD *)v6 + 148) = 0;
  *((_QWORD *)v6 + 77) = 0;
  *((_QWORD *)v6 + 76) = 0;
  *((_QWORD *)v6 + 75) = 0;
  *((_DWORD *)v6 + 156) = 0;
  *((_DWORD *)v6 + 145) = 0;
  *((_QWORD *)v6 + 73) = 0;
  *((_QWORD *)v6 + 5) = 0;
  *((_QWORD *)v6 + 11) = 0;
  *((_QWORD *)v6 + 12) = 0;
  *((_QWORD *)v6 + 14) = 0;
  *((_QWORD *)v6 + 13) = 0;
  *((_QWORD *)v6 + 15) = 0;
  *((_QWORD *)v6 + 16) = 0;
  *((_QWORD *)v6 + 17) = 0;
  *((_DWORD *)v6 + 44) = 15;
  *((_QWORD *)v6 + 23) = 60;
  *((_DWORD *)v6 + 45) = 3;
  *((_DWORD *)v6 + 48) = 0;
  *(_QWORD *)(v6 + 196) = 552;
  *(_QWORD *)(v6 + 204) = 8;
  *(_QWORD *)(v6 + 220) = 0;
  *((_QWORD *)v6 + 29) = 0;
  *((_QWORD *)v6 + 30) = 0;
  *((_DWORD *)v6 + 62) = 0;
  *((_QWORD *)v6 + 32) = 0;
  *((_QWORD *)v6 + 21) = 2;
  *((_DWORD *)v6 + 67) = 0;
  *((_QWORD *)v6 + 35) = 0;
  v8 = DtlCreateList();
  *((_QWORD *)v6 + 37) = v8;
  if ( !v8 )
  {
LABEL_18:
    DestroyEntryNode(v6);
    return 0;
  }
  *((_DWORD *)v6 + 76) = 1;
  *((_DWORD *)v6 + 77) = 1;
  *((_QWORD *)v6 + 39) = 0;
  *((_QWORD *)v6 + 40) = 0;
  *((_QWORD *)v6 + 41) = 0;
  *((_QWORD *)v6 + 42) = 0;
  *((_QWORD *)v6 + 43) = 0;
  *((_DWORD *)v6 + 88) = 1;
  *((_DWORD *)v6 + 89) = 1;
  *((_DWORD *)v6 + 96) = 0;
  *((_DWORD *)v6 + 97) = 1;
  *((_QWORD *)v6 + 49) = 0;
  *((_DWORD *)v6 + 100) = 0;
  *((_DWORD *)v6 + 101) = 1;
  *((_DWORD *)v6 + 112) = 0;
  *((_QWORD *)v6 + 52) = 0;
  *((_QWORD *)v6 + 53) = 0;
  *((_DWORD *)v6 + 102) = 1;
  *((_DWORD *)v6 + 90) = IsServerOS() != 0;
  *(_QWORD *)(v6 + 364) = 1;
  *((_QWORD *)v6 + 47) = 0;
  *(_QWORD *)(v6 + 452) = 0;
  *((_QWORD *)v6 + 58) = 0;
  *((_QWORD *)v6 + 59) = 0;
  *((_QWORD *)v6 + 60) = 0;
  *((_DWORD *)v6 + 122) = GetTickCount();
  v9 = (UUID *)GlobalAlloc(0x40u, 0x10u);
  *((_QWORD *)v6 + 62) = v9;
  if ( v9 )
    UuidCreate(v9);
  *((_QWORD *)v6 + 63) = 0;
  *((_QWORD *)v6 + 64) = 0;
  *(_QWORD *)(v6 + 572) = 0;
  *((_QWORD *)v6 + 80) = 0;
  *(_QWORD *)(v6 + 628) = 0;
  *((_QWORD *)v6 + 82) = 0;
  *((_QWORD *)v6 + 81) = 0;
  *((_QWORD *)v6 + 85) = 0;
  *((_DWORD *)v6 + 168) = 0;
  *((_DWORD *)v6 + 166) = 0;
  *((_QWORD *)v6 + 89) = 0;
  *((_QWORD *)v6 + 88) = 0;
  *((_QWORD *)v6 + 87) = 0;
  *((_QWORD *)v6 + 86) = 0;
  *((_QWORD *)v6 + 91) = 0;
  *((_QWORD *)v6 + 90) = 0;
  *((_QWORD *)v6 + 94) = 0;
  *(_QWORD *)(v6 + 740) = 0;
  *((_QWORD *)v6 + 96) = 0;
  *((_QWORD *)v6 + 95) = 0;
  *((_QWORD *)v6 + 97) = 0;
  *((_DWORD *)v6 + 184) = 0;
  *((_QWORD *)v6 + 99) = 0;
  *((_QWORD *)v6 + 101) = 0;
  *((_QWORD *)v6 + 100) = 0;
  *((_DWORD *)v6 + 204) = 0;
  *((_QWORD *)v6 + 105) = 0;
  *((_QWORD *)v6 + 107) = 0;
  *((_QWORD *)v6 + 110) = 0;
  *((_DWORD *)v6 + 222) = 0;
  *((_DWORD *)v6 + 216) = 0;
  *((_QWORD *)v6 + 109) = 0;
  *((_QWORD *)v6 + 122) = 0;
  *((_QWORD *)v6 + 113) = 0;
  *((_QWORD *)v6 + 115) = 0;
  *((_QWORD *)v6 + 112) = 0;
  *((_QWORD *)v6 + 114) = 0;
  *((_DWORD *)v6 + 233) = 1;
  *((_DWORD *)v6 + 232) = 0;
  *((_DWORD *)v6 + 234) = 0;
  *((_DWORD *)v6 + 236) = 0;
  *((_QWORD *)v6 + 119) = 0;
  *((_QWORD *)v6 + 120) = 0;
  *((_QWORD *)v6 + 123) = 0;
  *(_QWORD *)(v6 + 564) = 0;
  *((_QWORD *)v6 + 124) = 0;
  *(_QWORD *)(v6 + 1020) = 0;
  *((_DWORD *)v6 + 250) = 0;
  *((_QWORD *)v6 + 129) = 0;
  *(_OWORD *)(v6 + 1004) = 0;
  UpdateEntryTimeStamp(v6 + 32);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_38cda081c674317ed40163d707084d83_Traceguids);
  }
  return v6;
}

```

## disassembly

```asm
0x180006ce0  push    rbx
0x180006ce2  push    rbp
0x180006ce3  push    rsi
0x180006ce4  push    rdi
0x180006ce5  push    r14
0x180006ce7  sub     rsp, 20h
0x180006ceb  mov     esi, ecx
0x180006ced  mov     rcx, cs:WPP_GLOBAL_Control
0x180006cf4  lea     r14, WPP_GLOBAL_Control
0x180006cfb  xor     ebp, ebp
0x180006cfd  cmp     rcx, r14
0x180006d00  jnz     loc_1800070B3
0x180006d06  mov     ebx, 410h
0x180006d0b  mov     ecx, 40h ; '@'; uFlags
0x180006d10  mov     edx, ebx; dwBytes
0x180006d12  call    cs:__imp_GlobalAlloc
0x180006d18  mov     rdi, rax
0x180006d1b  test    rax, rax
0x180006d1e  jz      loc_18000713E
0x180006d24  mov     r8d, ebx; Size
0x180006d27  xor     edx, edx; Val
0x180006d29  mov     rcx, rax; void *
0x180006d2c  call    memset_0
0x180006d31  lea     rbx, [rdi+20h]
0x180006d35  mov     [rdi+10h], rbx
0x180006d39  call    DtlCreateList
0x180006d3e  mov     [rbx+20h], rax
0x180006d42  test    rax, rax
0x180006d45  jz      loc_180007136
0x180006d4b  test    esi, esi
0x180006d4d  jnz     loc_1800070F5
0x180006d53  mov     esi, 1
0x180006d58  mov     dword ptr [rbx], 0FFFFFFFFh
0x180006d5e  mov     [rbx+18h], esi
0x180006d61  mov     [rbx+28h], rsi
0x180006d65  mov     [rbx+30h], esi
0x180006d68  mov     [rbx+70h], esi
0x180006d6b  mov     [rbx+7Ch], esi
0x180006d6e  mov     [rbx+74h], rsi
0x180006d72  mov     [rbx+84h], esi
0x180006d78  mov     [rbx+0B4h], rsi
0x180006d7f  mov     [rbx+0F0h], esi
0x180006d85  mov     [rbx+0F4h], esi
0x180006d8b  mov     [rbx+230h], ebp
0x180006d91  mov     [rbx+248h], rbp
0x180006d98  mov     [rbx+240h], rbp
0x180006d9f  mov     [rbx+238h], rbp
0x180006da6  mov     [rbx+250h], ebp
0x180006dac  mov     [rbx+224h], ebp
0x180006db2  mov     [rbx+228h], rbp
0x180006db9  mov     [rbx+8], rbp
0x180006dbd  mov     [rbx+38h], rbp
0x180006dc1  mov     [rbx+40h], rbp
0x180006dc5  mov     [rbx+50h], rbp
0x180006dc9  mov     [rbx+48h], rbp
0x180006dcd  mov     [rbx+58h], rbp
0x180006dd1  mov     [rbx+60h], rbp
0x180006dd5  mov     [rbx+68h], rbp
0x180006dd9  mov     dword ptr [rbx+90h], 0Fh
0x180006de3  mov     qword ptr [rbx+98h], 3Ch ; '<'
0x180006dee  mov     dword ptr [rbx+94h], 3
0x180006df8  mov     [rbx+0A0h], ebp
0x180006dfe  mov     qword ptr [rbx+0A4h], 228h
0x180006e09  mov     qword ptr [rbx+0ACh], 8
0x180006e14  mov     [rbx+0BCh], rbp
0x180006e1b  mov     [rbx+0C8h], rbp
0x180006e22  mov     [rbx+0D0h], rbp
0x180006e29  mov     [rbx+0D8h], ebp
0x180006e2f  mov     [rbx+0E0h], rbp
0x180006e36  mov     qword ptr [rbx+88h], 2
0x180006e41  mov     [rbx+0ECh], ebp
0x180006e47  mov     [rbx+0F8h], rbp
0x180006e4e  call    DtlCreateList
0x180006e53  mov     [rbx+108h], rax
0x180006e5a  test    rax, rax
0x180006e5d  jz      loc_180007136
0x180006e63  mov     [rbx+110h], esi
0x180006e69  mov     [rbx+114h], esi
0x180006e6f  mov     [rbx+118h], rbp
0x180006e76  mov     [rbx+120h], rbp
0x180006e7d  mov     [rbx+128h], rbp
0x180006e84  mov     [rbx+130h], rbp
0x180006e8b  mov     [rbx+138h], rbp
0x180006e92  mov     [rbx+140h], esi
0x180006e98  mov     [rbx+144h], esi
0x180006e9e  mov     [rbx+160h], ebp
0x180006ea4  mov     [rbx+164h], esi
0x180006eaa  mov     [rbx+168h], rbp
0x180006eb1  mov     [rbx+170h], ebp
0x180006eb7  mov     [rbx+174h], esi
0x180006ebd  mov     [rbx+1A0h], ebp
0x180006ec3  mov     [rbx+180h], rbp
0x180006eca  mov     [rbx+188h], rbp
0x180006ed1  mov     [rbx+178h], esi
0x180006ed7  call    IsServerOS
0x180006edc  mov     edx, ebp
0x180006ede  test    eax, eax
0x180006ee0  setnz   dl
0x180006ee3  mov     [rbx+148h], edx
0x180006ee9  mov     [rbx+14Ch], rsi
0x180006ef0  mov     [rbx+158h], rbp
0x180006ef7  mov     [rbx+1A4h], rbp
0x180006efe  mov     [rbx+1B0h], rbp
0x180006f05  mov     [rbx+1B8h], rbp
0x180006f0c  mov     [rbx+1C0h], rbp
0x180006f13  call    cs:__imp_GetTickCount
0x180006f19  lea     edx, [rsi+0Fh]; dwBytes
0x180006f1c  mov     [rbx+1C8h], eax
0x180006f22  lea     ecx, [rsi+3Fh]; uFlags
0x180006f25  call    cs:__imp_GlobalAlloc
0x180006f2b  mov     [rbx+1D0h], rax
0x180006f32  test    rax, rax
0x180006f35  jnz     loc_1800070E7
0x180006f3b  mov     [rbx+1D8h], rbp
0x180006f42  xorps   xmm0, xmm0
0x180006f45  mov     [rbx+1E0h], rbp
0x180006f4c  mov     rcx, rbx
0x180006f4f  mov     [rbx+21Ch], rbp
0x180006f56  mov     [rbx+260h], rbp
0x180006f5d  mov     [rbx+254h], rbp
0x180006f64  mov     [rbx+270h], rbp
0x180006f6b  mov     [rbx+268h], rbp
0x180006f72  mov     [rbx+288h], rbp
0x180006f79  mov     [rbx+280h], ebp
0x180006f7f  mov     [rbx+278h], ebp
0x180006f85  mov     [rbx+2A8h], rbp
0x180006f8c  mov     [rbx+2A0h], rbp
0x180006f93  mov     [rbx+298h], rbp
0x180006f9a  mov     [rbx+290h], rbp
0x180006fa1  mov     [rbx+2B8h], rbp
0x180006fa8  mov     [rbx+2B0h], rbp
0x180006faf  mov     [rbx+2D0h], rbp
0x180006fb6  mov     [rbx+2C4h], rbp
0x180006fbd  mov     [rbx+2E0h], rbp
0x180006fc4  mov     [rbx+2D8h], rbp
0x180006fcb  mov     [rbx+2E8h], rbp
0x180006fd2  mov     [rbx+2C0h], ebp
0x180006fd8  mov     [rbx+2F8h], rbp
0x180006fdf  mov     [rbx+308h], rbp
0x180006fe6  mov     [rbx+300h], rbp
0x180006fed  mov     [rbx+310h], ebp
0x180006ff3  mov     [rbx+328h], rbp
0x180006ffa  mov     [rbx+338h], rbp
0x180007001  mov     [rbx+350h], rbp
0x180007008  mov     [rbx+358h], ebp
0x18000700e  mov     [rbx+340h], ebp
0x180007014  mov     [rbx+348h], rbp
0x18000701b  mov     [rbx+3B0h], rbp
0x180007022  mov     [rbx+368h], rbp
0x180007029  mov     [rbx+378h], rbp
0x180007030  mov     [rbx+360h], rbp
0x180007037  mov     [rbx+370h], rbp
0x18000703e  mov     [rbx+384h], esi
0x180007044  mov     [rbx+380h], ebp
0x18000704a  mov     [rbx+388h], ebp
0x180007050  mov     [rbx+390h], ebp
0x180007056  mov     [rbx+398h], rbp
0x18000705d  mov     [rbx+3A0h], rbp
0x180007064  mov     [rbx+3B8h], rbp
0x18000706b  mov     [rbx+214h], rbp
0x180007072  mov     [rbx+3C0h], rbp
0x180007079  mov     [rbx+3DCh], rbp
0x180007080  mov     [rbx+3C8h], ebp
0x180007086  mov     [rbx+3E8h], rbp
0x18000708d  movups  xmmword ptr [rbx+3CCh], xmm0
0x180007094  call    UpdateEntryTimeStamp
0x180007099  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070a0  cmp     rcx, r14
0x1800070a3  jnz     short loc_180007110
0x1800070a5  mov     rax, rdi
0x1800070a8  add     rsp, 20h
0x1800070ac  pop     r14
0x1800070ae  pop     rdi
0x1800070af  pop     rsi
0x1800070b0  pop     rbp
0x1800070b1  pop     rbx
0x1800070b2  retn
0x1800070b3  test    byte ptr [rcx+1Ch], 80h
0x1800070b7  jz      loc_180006D06
0x1800070bd  cmp     byte ptr [rcx+19h], 6
0x1800070c1  jb      loc_180006D06
0x1800070c7  mov     rcx, [rcx+10h]
0x1800070cb  lea     r8, WPP_38cda081c674317ed40163d707084d83_Traceguids
0x1800070d2  test    esi, esi
0x1800070d4  mov     edx, 18h
0x1800070d9  setnz   r9b
0x1800070dd  call    WPP_SF_c
0x1800070e2  jmp     loc_180006D06
0x1800070e7  mov     rcx, rax; Uuid
0x1800070ea  call    cs:__imp_UuidCreate
0x1800070f0  jmp     loc_180006F3B
0x1800070f5  call    CreateLinkNode
0x1800070fa  test    rax, rax
0x1800070fd  jz      short loc_180007136
0x1800070ff  mov     rcx, [rbx+20h]
0x180007103  mov     rdx, rax
0x180007106  call    DtlAddNodeLast
0x18000710b  jmp     loc_180006D53
0x180007110  test    byte ptr [rcx+1Ch], 80h
0x180007114  jz      short loc_1800070A5
0x180007116  cmp     byte ptr [rcx+19h], 6
0x18000711a  jb      short loc_1800070A5
0x18000711c  mov     rcx, [rcx+10h]
0x180007120  lea     r8, WPP_38cda081c674317ed40163d707084d83_Traceguids
0x180007127  mov     edx, 19h
0x18000712c  call    WPP_SF_
0x180007131  jmp     loc_1800070A5
0x180007136  mov     rcx, rdi
0x180007139  call    DestroyEntryNode
0x18000713e  xor     eax, eax
0x180007140  jmp     loc_1800070A8
```
